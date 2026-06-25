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
            title: "The Temple Construction Committee",
            description:
                "In order to support the construction of our new temple, the " +
                "Thiruppani Seyal (Construction Works) Committee has been " +
                "established. This committee was created with the sole purpose " +
                "of making the temple restoration project a reality and will be " +
                "actively working towards this goal. We encourage all devotees " +
                "to get involved in the project. If you would like to contribute, " +
                "donations can be made out to Hatton National Bank (Nelliady), " +
                "Acct. 118020318297. Please also feel free to contact 021-226-6664 " +
                "for more information.",
            slides: [
                "/videos/VIDEO-2026-06-21-18-39-02.mp4",
                "/PHOTO-2026-06-21-18-40-16.jpg",
            ],

        },
        {
            title: "Construction Begins",
            description:
                "We are honoured to begin construction of a new temple. Please " +
                "enjoy videos and images of the process as well as milestones " +
                "of the construction process which are outlined below.", 
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
            title: "Construction of Ganapathi Sannithanam",
            description:
                "We have recently begun work on the Ganapathi sannithanam. " +
                "The site has been consecrated, and work on the foundation " +
                "is currently underway.",
            slides: [
                "/videos/VIDEO-2026-06-21-18-52-17.mp4",
                "/videos/VIDEO-2026-06-21-18-52-32.mp4",
                "/videos/VIDEO-2026-06-21-18-53-14.mp4",
                "/PHOTO-2026-06-21-18-50-18.jpg",
                "/PHOTO-2026-06-21-18-50-19.jpg",
                "/PHOTO-2026-06-21-18-50-20.jpg",
                "/PHOTO-2026-06-21-18-50-21.jpg",
                "/PHOTO-2026-06-21-18-50-22_1.jpg",
                "/PHOTO-2026-06-21-18-50-22_2.jpg",
                "/PHOTO-2026-06-21-18-50-22_3.jpg",
                "/PHOTO-2026-06-21-18-50-22_4.jpg",
                "/PHOTO-2026-06-21-18-50-22_5.jpg",
                "/PHOTO-2026-06-21-18-50-22_6.jpg",
                "/PHOTO-2026-06-21-18-50-22.jpg",
                "/PHOTO-2026-06-21-18-50-23_1.jpg",
                "/PHOTO-2026-06-21-18-50-23_2.jpg",
                "/PHOTO-2026-06-21-18-50-23.jpg",
                "/PHOTO-2026-06-21-18-51-09.jpg",
                "/PHOTO-2026-06-21-18-51-48.jpg",
                "/PHOTO-2026-06-21-18-51-58.jpg",
                "/PHOTO-2026-06-21-18-52-40.jpg",
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
        {
            title: "Other Notable Events",
            description:
                "In memory of the late Mr. Satchithanantham, a daily annadhanam " +
                "has been started by Mr. Satchithananthan Tilak on behalf of his " +
                "family. The offerings are distributed to devotees daily in the " +
                "Ganapathipillai Aashram on the western road.",
            slides: [
                "/PHOTO-2026-06-21-18-58-48.jpg",
                "/videos/VIDEO-2026-06-21-19-00-47.mp4",
                "/PHOTO-2026-06-21-19-00-38_1.jpg",
                "/PHOTO-2026-06-21-19-00-38_3.jpg",
                "/PHOTO-2026-06-21-19-00-38_4.jpg",
                "/PHOTO-2026-06-21-19-00-38_5.jpg",
                "/PHOTO-2026-06-21-19-01-09.jpg",
                "/PHOTO-2026-06-21-19-01-36.jpg",
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
