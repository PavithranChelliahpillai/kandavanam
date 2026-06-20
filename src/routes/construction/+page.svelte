<script>
    import Navbar from "../template/nav.svelte";
    import Navphone from "../template/navphone.svelte";
    import MediaQuery from "../MediaQuery.svelte";
    import Footer from "../template/footer.svelte";
    import CarouselSection from "./CarouselSection.svelte";

    // Sections render top-to-bottom in this order. The carousel/text sides
    // automatically alternate based on position, so just add an entry here.
    const sections = [
        {
            title: "Lorem Ipsum",
            description:
                "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed " +
                "do eiusmod tempor incididunt ut labore et dolore magna aliqua. " +
                "Ut enim ad minim veniam, quis nostrud exercitation ullamco " +
                "laboris nisi ut aliquip ex ea commodo consequat.",
            slides: [
                "/videos/vid02.mp4",
                "/videos/vid01.mp4",
                "/videos/VIDEO-2024-02-11-04-13-26.mp4",
                "/videos/vid03.mp4",
                "/videos/vid04.mp4",
                "/videos/vid05.mp4",
                "/videos/vid06.mp4",
                "/videos/vid07.mp4",
                "/videos/vid08.mp4",
                "/videos/vid09.mp4",
                "/videos/vid10.mp4",
                "/videos/vid11.mp4",
                "/videos/vid12.mp4",
                "/videos/vid13.mp4",
                "/videos/vid14.mp4",
            ],
        },
        {
            title: "Construction of Sanctum Sanctorum (மூலஸ்தானம்)",
            description:
                'The mulasthanam, or the "main sanctum" is the new, permanent ' +
                "home of the main idol: Shanmukar. Currently, progress is being " +
                "made in the construction of the karpagraham, arthamandapam, " +
                "mahamandapam, etc. The first stone was inaugurated on Jan 21st, " +
                "2019 commencing the construction of the mulasthanam. Thus, the " +
                "base is fully prepared for complete construction of the " +
                "mulasthanam with granite stones.",
            slides: [
                "/p1.webp",
                "/p3.webp",
                "/p4.webp",
                "/p5.webp",
                "/p7.webp",
                "/p8.webp",
                "/p9.webp",
            ],
        },
        {
            title: "West Side of Temple",
            description:
                "The west side of the temple is where the preparations of " +
                "stonework for the temple occurs. This includes carving, " +
                "designing, and the intricate shaping of decorative granite " +
                'pieces. Through the guidance from the "sthapathi" (architects), ' +
                "led by Mr. V. Karthik, the temple is being constructed in a " +
                'manner that honours the "shilpa shastra", a timeless detailing ' +
                "of Hindu temple construction.",
            slides: [
                "/p10.webp",
                "/p11.webp",
                "/p12.webp",
                "/p13.webp",
                "/p14.webp",
                "/p15.webp",
                "/p16.webp",
            ],
        },
        {
            title: "Temple Vision",
            description:
                "The grand temple is a large undertaking to build a permanent " +
                "home for Shankmukar that stands the test of time. Currently, our " +
                "focus lies on the mulasthanam, but our ultimate goal is to " +
                "complete similar grand constructions for the parivara murthis. " +
                "The mandapams will be completed, followed by the rajagopuram.",
            slides: [
                "/e1.webp",
                "/e2.webp",
                "/e3.webp",
                "/e4.webp",
                "/i1.webp",
                "/i2.webp",
                "/i3.webp",
            ],
        },
    ];
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
    {#each sections as section, i}
        <CarouselSection {...section} invert={i % 2 === 1} />
    {/each}
    <Footer></Footer>
</body>

<MediaQuery query="(max-width: 1280px)" let:matches>
    {#if matches}
        <style>
            h1 {
                font-size: 7vh !important;
            }
            #temple {
                width: 150%;
                position: relative;
                left: 50%;
                transform: translateX(-50%);
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
    img {
        box-sizing: border-box;
        width: 100%;
    }
    #phone {
        display: none;
    }
</style>
