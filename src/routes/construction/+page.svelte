<script>
    import Navbar from "../template/nav.svelte";
    import Navphone from "../template/navphone.svelte";
    import emblaCarouselSvelte from "embla-carousel-svelte";
    import Autoplay from "embla-carousel-autoplay";
    import MediaQuery from "../MediaQuery.svelte";
    import Footer from "../template/footer.svelte";
    import { fade } from 'svelte/transition';

    let options = { loop: true };
    let plugins = [
        Autoplay({ delay: 3000, stopOnInteraction: false }),
        Autoplay({ delay: 3000, stopOnInteraction: true }),
        Autoplay({ delay: 3000, stopOnInteraction: false }),
        Autoplay({ delay: 3000, stopOnInteraction: false }),
    ];

    let vidShowIndex = 0;
    const videos = [
        {idx: 0, link: '/videos/vid02.mp4'},
        {idx: 1, link: '/videos/vid01.mp4'},
        {idx: 2, link: '/videos/VIDEO-2024-02-11-04-13-26.mp4'},
        {idx: 3, link: '/videos/vid03.mp4'},
        {idx: 4, link: '/videos/vid04.mp4'},
        {idx: 5, link: '/videos/vid05.mp4'},
        {idx: 6, link: '/videos/vid06.mp4'},
        {idx: 7, link: '/videos/vid07.mp4'},
        {idx: 8, link: '/videos/vid08.mp4'},
        {idx: 9, link: '/videos/vid09.mp4'},
        {idx: 10, link: '/videos/vid10.mp4'},
        {idx: 11, link: '/videos/vid11.mp4'},
        {idx: 12, link: '/videos/vid12.mp4'},
        {idx: 13, link: '/videos/vid13.mp4'},
        {idx: 14, link: '/videos/vid14.mp4'},
    ];

    const prevSlide = () => {
        if(vidShowIndex === 0) {
            vidShowIndex = videos.length-1;
        } else {
            vidShowIndex -= 1;
        }
        console.log(vidShowIndex);
    };

    const nextSlide = () => {
        if(vidShowIndex === videos.length-1) {
            vidShowIndex = 0;
        } else {
            vidShowIndex += 1;
        }
        console.log(vidShowIndex);
    };
</script>

<svelte:head>
    <title>Kanthavanam Temple</title>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta
        name="description"
        content="Details of the ongoing granite temple construction project."
    />
    <meta name="keywords" content="Kandavanam, Kanthavanam, Kanthasamy, Temple, Sri Lanka, Polikandy">
    <meta name="author" content="Pavithran Chelliahpillai" />
    <meta name="robots" content="index,follow">
</svelte:head>

<body>
    <div id="phonebye" style="position: fixed; top: 0; z-index: 500;">
        <Navbar></Navbar>
    </div>
    <div id="phone" style="position: fixed; top: 0; z-index: 500;">
        <Navphone></Navphone>
    </div>
    <h1 style="padding: 2vh 0vw; padding-left: 1vw;" id="title">
        Temple Construction
    </h1>
    <img id="temple" src="../temple.webp" alt="" />
    <div class="flexbox">
        <div class="flexchild" style="padding-left: 5vw;">
            <h1 style="width: 80%;">
                Construction of Sanctum Sanctorum (மூலஸ்தானம்)
            </h1>
            <p>
                The mulasthanam, or the "main sanctum" is the new, permanent
                home of the main idol: Shanmukar. Currently, progress is being
                made in the construction of the karpagraham, arthamandapam,
                mahamandapam, etc. The first stone was inaugurated on Jan 21st,
                2019 commencing the construction of the mulasthanam. Thus, the
                base is fully prepared for complete construction of the
                mulasthanam with granite stones.
            </p>
        </div>
        <div class="flexchild" id="galleria-wrapper">
            <div
                class="flexchild"
                id="galleria"
                style="padding-top: 7vh; margin-right: 2vw;"
            >
                <div
                    class="embla"
                    use:emblaCarouselSvelte={{ options, plugins: [plugins[0]] }}
                >
                    <div class="embla__container">
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p1.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p3.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p4.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p5.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p7.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p8.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p9.webp"
                                alt="about us"
                            />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="flexbox">
        <div class="flexchild video-wrapper">
                {#each videos as {idx,link}
                    (idx)
                }
                    {#if vidShowIndex === idx}
                        <div class="video-container" style="z-index: 20" transition:fade>
                            <video
                                controls
                                autoplay
                            >
                                <source src={link} type="video/mp4" />
                            </video>
                        </div>
                    {/if}
                {/each}
                <a class="prev" on:click={prevSlide}>&#10094;</a>
                <a class="next" on:click={nextSlide}>&#10095;</a>
        </div>
    </div>
    <div class="flexbox" id="invert">
        <div
            class="flexchild"
            id="galleria-wrapper"
            style="padding-left: 2vw; "
        >
            <div
                class="flexchild"
                id="galleria"
                style="padding-top: 7vh; margin-right: 2vw;"
            >
                <div
                    class="embla"
                    use:emblaCarouselSvelte={{ options, plugins: [plugins[2]] }}
                >
                    <div class="embla__container">
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p10.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p11.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p12.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p13.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p14.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p15.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p16.webp"
                                alt="about us"
                            />
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="flexchild" style="padding-left: 5vw;">
            <h1 style="width: 80%;">West Side of Temple</h1>
            <p>
                The west side of the temple is where the preparations of
                stonework for the temple occurs. This includes carving,
                designing, and the intricate shaping of decorative granite
                pieces. Through the guidance from the "sthapathi" (architects),
                led by Mr. V. Karthik, the temple is being constructed in a
                manner that honours the "shilpa shastra", a timeless detailing
                of Hindu temple construction.
            </p>
        </div>
    </div>
    <div class="flexbox">
        <div class="flexchild" style="padding-left: 5vw;">
            <h1 style="width: 80%;">Temple Vision</h1>
            <p>
                The grand temple is a large undertaking to build a permanent
                home for Shankmukar that stands the test of time. Currently, our
                focus lies on the mulasthanam, but our ultimate goal is to
                complete similar grand constructions for the parivara murthis.
                The mandapams will be completed, followed by the rajagopuram.
            </p>
        </div>
        <div class="flexchild" id="galleria-wrapper">
            <div
                class="flexchild"
                id="galleria"
                style="padding-top: 7vh; margin-right: 2vw;"
            >
                <div
                    class="embla"
                    use:emblaCarouselSvelte={{ options, plugins: [plugins[2]] }}
                >
                    <div class="embla__container">
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\e1.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\e2.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\e3.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\e4.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\i1.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\i2.webp"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\i3.webp"
                                alt="about us"
                            />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <Footer></Footer>
</body>

<MediaQuery query="(max-width: 1280px)" let:matches>
    {#if matches}
        <style>
            .video-wrapper {
                max-width: 95%;
                height: auto;
            }
            .flexbox {
                display: block !important;
            }
            .flexchild {
                padding: 0 !important;
                margin: 0 !important;
            }
            #invert {
                display: flex !important;
                flex-direction: column-reverse !important;
            }
            .flexchild {
                align-items: center;
            }
            .flexchild h1 {
                text-align: center;
                margin-left: -6vw !important;
                font-size: 5vh !important;
                width: 100% !important;
                padding: 0 !important;
                margin: 0 !important;
                padding-top: 3vh !important;
            }
            .flexchild p {
                text-align: center;
                width: 90% !important;
                padding: 0 !important;
                margin-top: 1vh !important;
                padding-bottom: 3vh !important;
            }
            h1 {
                font-size: 7vh !important;
            }
            #temple {
                position: relative;
                width: 200%;
                left: -20% !important;
            }
            #phone {
                display: flex !important;
            }
            #phonebye {
                display: none !important;
            }
            #title {
                margin-top: 12vh !important;
            }
            body {
                overflow-x: hidden;
            }
        </style>
    {/if}
</MediaQuery>

<style>
    body {
        width: 100%;
    }
    h1 {
        font-size: 3vw;
        padding: 0;
        margin: 0;
        margin-top: 7vh;
        padding-left: 1vw;
        line-height: 7vh;
    }
    #temple {
        margin-top: 1vh;
    }
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
    img {
        box-sizing: border-box;
        width: 100%;
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
    .embla__slide img {
        object-fit: cover;
    }
    .video-wrapper {
        position: relative;
        width: 100%;
        max-width: 65%;
        height: 60vh;
        padding-top: 0;
        margin: 5vh auto;
        margin-bottom: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;
    }
    video {
        max-height: 100%;
        max-width: 100%;
        object-fit: contain;
    }
    .video-container {
        position: absolute;
        background: black;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .prev, .next {
        cursor: pointer;
        position: absolute;
        top: 50%;
        width: auto;
        transform: translateY(-50%);
        z-index:20;
        padding: 16px;
        color: white;
        font-weight: bold;
        font-size: 18px;
        transition: 0.6s ease;
        border-radius: 0 3px 3px 0;
        user-select: none;
    }
    .prev {
        left: 0.2rem;
    }
    .next {
        right: 0.2rem;
    }
    .prev:hover, .next:hover {
        background-color: rgba(0,0,0,0.8);
    }
    #phone {
        display: none;
    }
    img {
        max-width: 1000vw !important;
    }
</style>
