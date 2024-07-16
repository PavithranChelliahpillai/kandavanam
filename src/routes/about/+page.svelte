<script>
    import Navbar from "../template/nav.svelte";
    import Navphone from "../template/navphone.svelte";
    // @ts-ignore
    import Gallery from "svelte-image-gallery";
    import MediaQuery from "../MediaQuery.svelte";
    import Footer from "../template/footer.svelte"
</script>

<head>
    <title>About Us</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Origin and information about the temple and murthigal (idols).">
    <meta name="keywords" content="HTML, CSS, JavaScript">
    <meta name="author" content="Pavithran Chelliahpillai">
    <meta name="robots" content="index,follow">
</head>

<body>
    <div id="phonebye" style="position: fixed; top: 0; z-index: 500;">
        <Navbar></Navbar>
    </div>
    <div id="phone" style="position: fixed; top: 0; z-index: 500;">
        <Navphone></Navphone>
    </div>
    <h1 id="titre" style="padding-top: 8vh;">About Us</h1>
    <div id="bcont">
        <div class="flexboxh">
            <div class="flexboxv" id="words">
                <section class="container">
                    <h2>Temple History</h2>
                    <p>
                        The Temple has been maintained and administered by the
                        descendants of saivaite Thikam Chelliahpillai – a well
                        known person for his elegant writing of <i
                            >Saiva Sithantham</i
                        >. Due to his services to saivisim, (MVTF)
                        Thiruvavadurai had conferred him the tile
                        <i>Esanasivam</i>. Long back, upon the request of
                        G.G.Ponnambalam, he delivered a speech about the
                        importance and tenets of saivism in the parliament. It
                        was landed by many and culminated in the recognition of
                        saivism in Sri Lanka. Sir Pon. Ramanathan too had been a
                        good friend of S.Thikam Chelliahpillai. His efforts
                        regained the status of descendants of saivaites of
                        Thirumaraikadu, Vedaraniyam India, living at that time
                        at Varani, Jaffna.
                    </p>
                </section>
                <img
                        src="/a1.jpeg"
                        alt=""
                        class="phone"
                    />
                <section class="container">
                    <h2>The Moorthangal</h2>
                    <p>
                        The moorthangal are considered to be special. There are
                        three <i>Shanmugars</i>:
                        <i>Palayavar</i> – the old main deity, the prevailing
                        main deity, and the third one is called
                        <i>Arumuga Nasnar</i>. <i>Palayavar</i> was sculptured
                        by the sculptor <i>Silpamunivar</i>, one of the renowned
                        sculptors of Chola Emperor Era which ruled the south
                        India at that time. There was a specialty to this idol
                        which was sculptured after the sculptor's hand was cut
                        off by the King Mutaarasar. He held his chisel between
                        the shoulder-hand joint during the sculpturing process.
                        The other three idols sculptured by the same
                        <i>Silpamunivar</i> has been available at Sikkal, Eddikudi,
                        Emkan and South India.
                    </p>
                </section>
                <img
                        src="/a2.jpg"
                        alt=""
                        class="phone"
                    />
                <section class="container">
                    <h2>Poojas</h2>
                    <p>
                        The Shanmugar was first brought to "Mullaithavan" and
                        consecrated at "Kumarapuram" and then brought to
                        "Kandavanam" and subsequently consecrated and maintained
                        as main duty in temple. Approximately 100 years ago,
                        while doing abhishekam to Shanmugar, a pot had fallen
                        and tarnished the <i>Varatha Hand</i>
                        on the left side of the Shanmugar. As a purification process,
                        a new 'Shanmugar' of the same configuration had been brought
                        from Kumbakonam, India and it has been maintained as the
                        main deity. The <i>Arumuga Nainar</i> was moulded in the
                        temple itself. People had voluntarily contributed even
                        the Thirumangalyam to the metal mixture
                        <i>Iympon</i>. This Idol has been extraordinarily
                        beautiful and the largest of its kind.
                        <i>Kirubananda Variyar</i> while seeing the Idol wondered
                        and exhilarated on a visit to this temple.The poojas have
                        been performed by the descendants of brahmins of Kumbakonam,
                        India now living at Nayindal, Jaffna District.
                    </p>
                </section>
                <img
                        src="/a3.jpg"
                        alt=""
                        class="phone"
                    />
                <section class="container">
                    <h2>The Temple Pond</h2>
                    <p>
                        It is called as <i>Narundeerakeni</i> and believed to be
                        formed by Veeraragava Thevar by using his Thandam. It
                        was believed to be producing 'Camphor' – coming from the
                        middle of the pond. But it stopped once the Portugese
                        people stepped into the temple. Hence the name for his
                        temple
                        <i>Karpoora Kanthan</i>.
                        <i>Sthala Virucham</i> (temple tree) is a vanni tree. There
                        have been three vanni trees of which two are said to be 2000
                        years old. Kandavanam Temple had been known for its special
                        features of offering child birth to parents. The childless
                        parent had to eat the mango fruit obtained from the mango
                        tree available in the temple premises. This tree as seeding
                        was said to be brought form Kanchipuram, India. Hence the
                        name 'Kanchima'. The children born one of the blessings of
                        shanmugar were named after Shanmugar synonyms like – 'Kandavanam',
                        'Kalyana velan', 'Kanchima Vadivel', 'Skandaraniyan' etc.
                    </p>
                </section>
                <img
                        src="/a4.jpg"
                        alt=""
                        class="phone"
                    />
                <section class="container">
                    <h2>The Theer</h2>
                    <p>
                        The Theer of this temple is very big and equal in size
                        of the "theer" of 'Mavidapuram" Kandasamy temple. Still
                        this Theer is in running condition and the festival has
                        been famous in this temple. Many sidhars, saints and
                        pandits had worshiped and performed miracles in this
                        temple. During the earlier period, temple had three car
                        street around the temple, however during the Portugese
                        rule it was reduced to two car streets – which are wide
                        and beautiful and compared with "Thiruvarur, India
                        Theer". The saying goes, 'Beautiful is Thiruvarur Theer,
                        Beautiful is Kandavanam koil Street".
                    </p>
                </section>
                <img
                        src="/a5.jpg"
                        alt=""
                        class="phone"
                    />
                <section class="container">
                    <h2>Festival</h2>
                    <p>
                        Annual Festival starts with June, Amavasaya and ends
                        with full moon day with
                        <i>Theertha Festival</i>. Kanda Sasti starts with
                        raising the temple flag and the last day will be
                        soorasamkaram. The very next day will be Thirukalyanam.
                        This type of Kantha sasthi festival is very unique and
                        this temple is known for it. After thirukalyanam the
                        temple flag will be lowered.
                    </p>
                </section>
            </div>
            <div
                class="flexboxv"
                style="flex: 1 1 0px; flex-grow: 1; flex-direction: column;"
                id="gallery"
            >
                <Gallery>
                    <img
                        src="/a1.jpeg"
                        alt=""
                    />
                    <img
                        src="/a2.jpg"
                        alt=""
                    />
                    <img
                        src="/a3.jpg"
                        alt=""
                    />
                    <img
                        src="/a4.jpg"
                        alt=""
                    />
                    <img
                        src="/a5.jpg"
                        alt=""
                    />
                    <img
                        src="/a1.jpeg"
                        alt=""
                    />
                    <img
                        src="/a2.jpg"
                        alt=""
                    />
                    <img
                        src="/a3.jpg"
                        alt=""
                    />
                    <img
                        src="/a4.jpg"
                        alt=""
                    />
                    <img
                        src="/a5.jpg"
                        alt=""
                    />
                </Gallery>
            </div>
        </div>
    </div>
    <Footer></Footer>
</body>

<style>
    body {
        line-height: 1.5;
        width: 100%;
        /* overflow: visible !important;  */
    }
    img { 
        box-sizing: border-box;
    }
    #bcont {
        display: flex;
        flex-direction: column;
        flex-basis: 100%;
    }
    .flexboxv {
        display: flex;
        flex-direction: column;
        padding: 0;
        margin: 0;
        flex: 1; /* Each child takes up an equal share of the available space */
        justify-content: start;
        align-items: flex-start;
    }
    .flexboxh {
        display: flex;
        flex-direction: row;
        flex-basis: 90%;
    }

    h1 {
        margin: none;
        font-size: 5vh;
        margin: 0;
        margin-left: 1vw;
        padding: none;
    }

    h2 {
        font-size: 3vh;
        margin: 0;
    }

    p {
        padding: 0;
        margin: 0;
    }

    .container {
        padding: 1%;
        margin: 1%;
        border-radius: 25px;
        color: #722620;
        background-color: #ffd08e;
        box-sizing: border-box; 
    }
    #words {
        width: 60vw;
    }
    .phone { 
        display: none; 
    }
    #phone { 
        display: none; 
    }
</style>

<MediaQuery query="(max-width: 1280px)" let:matches>
    {#if matches}
        <style>
            body, html {
                position: relative !important; 
                overflow-x: hidden !important;
                width: 100vw !important;
            }
            .flexboxh {
                display: inline !important; 
            }
            .container { 
                margin: 1vh 0vw !important; 
                padding: 1vh 1vw !important; 
            }
            #bcont {
                display: inline !important;
            }
            #words {
                width: 100vw !important;
            }
            #gallery { 
                display: none; 
            }
            .phone { 
                display: block !important; 
                box-sizing: border-box; 
                width: 100%; 
            }
            #phone { 
                display: flex !important; 
            }
            #phonebye { 
                display: none !important; 
            }
            #titre { 
                margin-top: 12vh; 
                padding: 0 !important; 
            }
        </style>
    {/if}
</MediaQuery>