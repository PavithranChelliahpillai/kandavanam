<script>
    import emblaCarouselSvelte from "embla-carousel-svelte";
    import { onDestroy } from "svelte";

    /** @type {string} Section heading */
    export let title;
    /** @type {string} Description paragraph shown beside the carousel */
    export let description;
    /**
     * Slides for the carousel. Each entry is either:
     *  - a string path (type is auto-detected from the file extension), or
     *  - an object { type: "image" | "video", src: string }
     * @type {(string | { type: "image" | "video", src: string })[]}
     */
    export let slides = [];
    /** @type {boolean} When true, the carousel is on the left and text on the right */
    export let invert = false;
    /** @type {number} How long (ms) image slides stay before advancing */
    export let delay = 3000;

    const options = { loop: true };

    const isVideo = (src) => /\.(mp4|webm|ogg|mov|m4v)$/i.test(src);

    // Normalize the slides into { type, src } objects
    $: media = slides.map((s) =>
        typeof s === "string"
            ? { type: isVideo(s) ? "video" : "image", src: s }
            : s
    );

    let emblaApi;
    let videoEls = [];
    let timer;

    const clearTimer = () => {
        clearTimeout(timer);
        timer = undefined;
    };

    // Advance to the next slide. Images use a timer; videos wait until they end.
    const handleSelect = () => {
        clearTimer();
        if (!emblaApi) return;

        const idx = emblaApi.selectedScrollSnap();

        // Pause/reset every video that isn't the active slide
        videoEls.forEach((v, j) => {
            if (v && j !== idx) {
                v.pause();
                v.currentTime = 0;
            }
        });

        const current = media[idx];
        if (current && current.type === "video") {
            const v = videoEls[idx];
            if (v) {
                v.muted = true;
                v.currentTime = 0;
                // Muted autoplay is allowed; fall back to the timer if it's blocked
                Promise.resolve(v.play()).catch(() => {
                    timer = setTimeout(() => emblaApi.scrollNext(), delay);
                });
            } else {
                timer = setTimeout(() => emblaApi.scrollNext(), delay);
            }
        } else {
            timer = setTimeout(() => emblaApi.scrollNext(), delay);
        }
    };

    const handleVideoEnded = (i) => {
        if (emblaApi && emblaApi.selectedScrollSnap() === i) {
            emblaApi.scrollNext();
        }
    };

    const onEmblaInit = (event) => {
        emblaApi = event.detail;
        emblaApi.on("select", handleSelect);
        emblaApi.on("reInit", handleSelect);
        handleSelect();
    };

    onDestroy(clearTimer);
</script>

<div class="flexbox" class:invert>
    <div class="flexchild text">
        <h1>{title}</h1>
        <p>{description}</p>
    </div>
    <div class="flexchild galleria-wrapper">
        <div class="flexchild galleria">
            <div
                class="embla"
                use:emblaCarouselSvelte={{ options }}
                on:emblaInit={onEmblaInit}
            >
                <div class="embla__container">
                    {#each media as item, i}
                        <div class="embla__slide">
                            {#if item.type === "video"}
                                <!-- svelte-ignore a11y-media-has-caption -->
                                <video
                                    bind:this={videoEls[i]}
                                    src={item.src}
                                    controls
                                    muted
                                    playsinline
                                    preload="metadata"
                                    on:ended={() => handleVideoEnded(i)}
                                ></video>
                            {:else}
                                <img src={item.src} alt={title} />
                            {/if}
                        </div>
                    {/each}
                </div>
            </div>
        </div>
    </div>
</div>

<style>
    .flexbox {
        padding: 0;
        margin: 0;
        position: relative;
        display: flex;
        flex-direction: row;
    }
    .flexchild {
        padding: 0;
        margin: 0;
        flex: 1 1 0px;
        flex-grow: 1;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
    .text {
        padding-left: 5vw;
    }
    /* Invert swaps the visual order: carousel left, text right */
    .flexbox.invert .text {
        order: 2;
    }
    .flexbox.invert .galleria-wrapper {
        order: 1;
        padding-left: 2vw;
    }
    .galleria {
        padding-top: 7vh;
        margin-right: 2vw;
    }
    h1 {
        font-size: 3vw;
        padding: 0;
        margin: 0;
        margin-top: 7vh;
        padding-left: 1vw;
        line-height: 7vh;
        width: 80%;
    }
    p {
        padding: 0;
        margin: 0;
        padding-left: 1vw;
        font-size: 2vh;
        padding-top: 1vh;
        line-height: 3vh;
        width: 60%;
        padding-bottom: 3vh;
    }
    img,
    video {
        box-sizing: border-box;
        width: 100%;
        height: 100%;
        object-fit: cover;
        display: block;
    }
    video {
        border: 5px solid #ffd08e;
        border-radius: 20px;
        background: #000;
    }
    .embla {
        overflow: hidden;
    }
    .embla__container {
        display: flex;
        grid-auto-flow: column;
        grid-auto-columns: 40%;
    }
    .embla__slide {
        flex: 0 0 100%;
        min-width: 0;
        height: 60vh;
        transition-timing-function: linear;
    }

    @media (max-width: 1280px) {
        /* Stack on mobile: text on top, carousel below (both layouts) */
        .flexbox,
        .flexbox.invert {
            display: block;
        }
        .flexbox.invert .text,
        .flexbox.invert .galleria-wrapper {
            order: 0;
            padding-left: 0;
        }
        .flexchild {
            padding: 0;
            margin: 0;
            align-items: center;
        }
        .text {
            padding-left: 0;
        }
        h1 {
            text-align: center;
            margin-left: -6vw;
            font-size: 5vh;
            width: 100%;
            padding: 0;
            margin: 0;
            padding-top: 3vh;
        }
        p {
            text-align: center;
            width: 90%;
            padding: 0;
            margin-top: 1vh;
            padding-bottom: 3vh;
        }
    }
</style>
