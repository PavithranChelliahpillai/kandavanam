<script>
    import Navbar from "../template/nav.svelte";
    import Navphone from "../template/navphone.svelte";
    import emblaCarouselSvelte from "embla-carousel-svelte";
    import Autoplay from "embla-carousel-autoplay";
    import MediaQuery from "../MediaQuery.svelte";
    import Footer from "../template/footer.svelte";

    let options = { loop: true };
    let plugins = [
        Autoplay({ delay: 3000, stopOnInteraction: false }),
        Autoplay({ delay: 3000, stopOnInteraction: false }),
        Autoplay({ delay: 3000, stopOnInteraction: false }),
    ];
</script>

<head>
    <title>Kanthavanam Temple</title>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta
        name="description"
        content="Details of the ongoing granite temple construction project."
    />
    <meta name="keywords" content="HTML, CSS, JavaScript" />
    <meta name="author" content="Pavithran Chelliahpillai" />
    <meta name="robots" content="index,follow">
</head>

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
    <img id="temple" src="../temple.png" alt="" />
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
                                src="\p1.JPG"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p3.JPG"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p4.JPG"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p5.JPG"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p7.JPG"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p8.JPG"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p9.JPG"
                                alt="about us"
                            />
                        </div>
                    </div>
                </div>
            </div>
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
                    use:emblaCarouselSvelte={{ options, plugins: [plugins[1]] }}
                >
                    <div class="embla__container">
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p10.jpg"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p11.jpg"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p12.jpg"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p13.jpg"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p14.jpg"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p15.jpg"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\p16.jpg"
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
                                src="\e1.jpg"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\e2.jpg"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\e3.jpg"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\e4.jpg"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\i1.jpg"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\i2.jpg"
                                alt="about us"
                            />
                        </div>
                        <div class="embla__slide">
                            <img
                                style="width: 100%; height: 100%"
                                src="\i3.jpg"
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
    #phone {
        display: none;
    }
    img {
        max-width: 1000vw !important;
    }
</style>
