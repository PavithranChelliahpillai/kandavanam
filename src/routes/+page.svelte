<!-- IMPROVE ALL MARQUEES! -->

<script>
    import { Marquee } from "@selemondev/svelte-marquee";
    import "@selemondev/svelte-marquee/dist/style.css";
    import Navbar from "./template/nav.svelte";
    import Navphone from "./template/navphone.svelte";
    import MediaQuery from "./MediaQuery.svelte";

    let donors = [
        "செல்வி.நவரட்ணம் சசிகலா Rs.3500000",
        "திருமதி.நவரட்ணம் இராசமலர் Rs.1000000",
        "க.திலகவதி, உ.விஜியராணி Rs.1000000",
        "சந்திரலிங்கம் செல்வராணி இந்தியா Rs.500000",
        "சின்னையா மயூரன் Rs.500000",
        "மு.ஜெகநாதன் குடும்பம் Rs.500000",
        "சின்னத்தம்பி சிவராசா Rs.225000",
        "கதிரன் இராசன் Rs.225000",
        "பஞ்சரத்தினம் பன்னீர்செல்வம் Rs.225000",
        "கிட்டிணன் சிவதாஸ் Rs.225000",
        "இராசேந்திரம் இராஜவேந்தன் Rs.225000",
        "குண்டுமணி புஸ்பகன் Rs.225000",
        "புஸ்பகன் சிவதர்சினி Rs.225000",
        "கிட்டிணன் நற்குணம் Rs.225000",
        "மாணிக்கம் யோகேஸ்வரன் Rs.225000",
        "சின்னட்டி கந்தசாமி Rs.225000",
        "இராசலிங்கம் தினேஸ் Rs.225000",
        "தம்பையா விமல் Rs.300000",
        "சிவக்கொழுந்து சிவானந்தபிரகாஸ் Rs.225000",
        "கந்தையா சிவகுமார் Rs.225000",
        "பாஸ்கரன் பொலிகை புத்தகசாலை சாவச்சேரி Rs.110000",
        "அமரர் க.முருகதாஸ் ஞாபகார்த்தமாக மு.அம்மன்கிளி குடும்பம் Rs.100000",
        "சிவகுமார் பிருந்தா Rs.100000",
        "யு.மு.சுப்பிரமணியம், இந்திரபூபதி Rs.100000",
        "நா.இராமச்சந்திரன் குடும்பம் Rs.100000",
        "ஜெயராசா அனிதா Rs.100000",
        "வேலாயுதம்பிள்ளை சாந்தி Rs.100000",
        "அ.ஆறுமுகம் இளையாணன் Rs.100000",
        "ஜெயாமோட்டோர்ஸ் ச.ரத்தினகோபால் Rs.50000",
        "சசீஸ்தரன் - யனுஷன் Rs.50000",
        "தில்லைநாதன் குடும்பம் Rs.50000",
        "தர்சிகா கிருபாகரன் Rs.50000",
        "ராதாவதி சிவபாதம் Rs.50000",
        "ஆச.ளுரளாடையனநஎi Rs.50000",
        "சுபாஷ் அஜந்தா Rs.50000",
        "சின்னத்தம்பி மயில்வாகனன் குடும்பம் Rs.25000",
        "திருமதி.விஜயராணி உருத்திரேஸ்வரன் Rs.25000",
        "ந.தெய்வேந்திரராஜா Rs.25000",
        "நவரட்ணம் கவிதாசன் Rs.25000",
        "ஸ்ரீசித்திர வேலாயுதர் ஆலயம் Rs.25000",
        "வினாயகமூர்த்தி பிரதீபன் குடும்பம் Rs.25000",
        "நடராசா கனகசபை ஆசிரியர் குடும்பம் பலாவித்தெரு பொலிகண்டி Rs.30000",
        "கனகசபை ஆசிரியர் குடும்பம் Rs.30000",
        "மகேந்திரராணி இளங்கோ Rs.30000",
        "வீரசுந்தரம் குடும்பம் Rs.30000",
        "ஆறுமுகம் ஆழ்வாப்பிள்ளை Rs.13500",
        "பா.ஜெயகுமார் Rs.27000",
        "சாந்தகுமார் Rs.13000",
        "இராசலச்சுமி Rs.12000",
        "கந்தையா குடும்பம் கொண்டைக்கட்டை வல்வெட்டித்துறை Rs.10000",
        "குமாரசாமி கதிர்காமத்தம்பி Rs.10000",
        "கதிர்காமத்தம்பி பருத்தித்துறை Rs.10000",
        "செ.தையல்நாயகி Rs.10000",
        "ந.சபாரத்தினம் Rs.10000",
        "த.யாமோதரன் Rs.10000",
        "கந்தையா குடும்பம் Rs.10000",
        "கு.கதிர்காமத்தம்பி Rs.10000",
        "பொன்னம்பலம் வள்ளிராணி Rs.25000",
        "செல்வவிநாயகம் குடும்பம் Rs.5000",
        "கு.கார்த்தீபன் Rs.5000",
        "ந.நடேசரத்தினம் பானுமதி Rs.5000",
        "பொ.சக்திவேல் Rs.5000",
        "குகன் குடிசை Rs.5000",
        "உதயணன் தர்ஸிதா Rs.5000",
        "த.தர்மிளன், த.சாத்விகன் Rs.5000",
        "தன்னைநாதன் பார்வதி Rs.5000",
        "இராஜசிங்கம் விஜயலக்சுமி Rs.5000",
        "புவனேந்திரன் இளம்பரிதி Rs.5000",
        "சு.ஜெயகங்கா Rs.5100",
        "சிவபாக்கியம் குடும்பம் Rs.1000",
        "சி.பாலசுந்தரம் Rs.1000",
        "அ.அவிஸ் Rs.1000",
        "குகன்குடிசை அன்பர் Rs.1000",
        "த.கணேசலிங்கம் Rs.1000",
        "பொ.பாலச்சந்திரன் Rs.1000",
        "த.சுஜீவன் Rs.1000",
        "முத்தையா யோகலட்சுமி Rs.1000",
        "சி.யசோதரன் Rs.1000",
        "சி.றஞ்சன் Rs.1000",
        "பொன்னம்பலம் சிவானந்தம் Rs.1000",
        "சங்கரகாந்தலிங்கம் Rs.1000",
        "இ.இராசமலர் Rs.1000",
        "சீவரத்தினம், ஐங்கரன் Rs.1000",
        "N.சோபினி Rs.1000",
        "த.சுசீபன் Rs.1000",
        "சிவகுமார் சுமதி Rs.1000",
        "த.சின்னராசா Rs.1000",
        "இலங்கநாதன் குடும்பம் Rs.1000",
        "ம.சிவகுகன் Rs.200",
        "தி.சரஸ்வதி Rs.500",
        "த.சுவேந்திரன் Rs.500",
        "அ.குமராதவன் Rs.500",
        "ஸ்ரீ.நிலாதரன் Rs.500",
        "சி.இராசகுலேந்திரன் Rs.600",
        "பா.கீர்த்தனா Rs.500"
    ];


</script>

<svelte:head>
    <title>Kanthavanam Temple</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Official website of Arulmigu Kanthavanam Kanthasamy Temple, Sri Lanka.">
    <meta name="keywords" content="Kandavanam, Kanthavanam, Kanthasamy, Temple, Sri Lanka, Polikandy">
    <meta name="author" content="Pavithran Chelliahpillai">
    <meta name="robots" content="index,follow">
</svelte:head>

<body>
    <img src="\muruganfrontimg.webp" id="murugan" alt="murugan" />
    <div id="phonebye" style="position: fixed; top: 0; z-index: 500;">
        <Navbar></Navbar>
    </div>
    <div id="phone" style="position: fixed; top: 0; z-index: 500;">
        <Navphone></Navphone>
    </div>
    <h1 id="bigtitle" style="position: relative; padding-top: 1vh;">
        <span>Arulmigu </span>
        <span>Kanthavanam</span>
        <span>Kanthasamy</span>
        <span>Temple</span>
    </h1>

    <section id="posts">
        <section id="construction">
            <h2>Temple Construction</h2>
            <p style="font-size: 1vw; padding-right: 2%;">
                The Kandavanam Temple is the home of Arumuga Swamy. For over 100
                years, temple caretakers have aspired to build a granite
                long-lasting, permanent temple for Arumuga Swamy. As of today,
                the Mulasthanam is under construction. You can participate in
                the construction of this temple - a once in a lifetime
                opportunity.
            </p>
        </section>
        <section id="donors">
            <h2 style="padding-bottom: 1vh;">Donors</h2>
            <div style="padding-left: 1vw;">
                <Marquee direction="up" fade={false} duration={600}>
                    {#each donors as donor}
                        <div style="font-size: 2vh;">{donor}</div>
                    {/each}
                </Marquee>
            </div>
        </section>
        <section id="events">
            <h2>Events</h2>
            <div style="padding-left: 1vw;">
                <Marquee direction="up" fade={true} class="[--duration:12s]">
                    <div>Thai Pusam</div>
                    <div>Masi Maham</div>
                    <div>Panguni Uttaram</div>
                    <div>Vaikhasi Visaham</div>
                    <div>Ani Brahmotsavam</div>
                    <div>Navaratri</div>
                    <div>Kanda Shasti</div>
                    <div>Annabhishekam (Aipasi Pournami)</div>
                    <div>Thiruvembavai</div>
                    <div>Monthly Karthikai Uttsavam</div>
                </Marquee>
            </div>
        </section>
        <section id="dpujas">
            <h2>Daily Pujas</h2>
            <div style="padding-left: 1vw; height: 100%;">
                <Marquee direction="up" fade={true} class="[--duration:12s]">
                    <div>Vishvaruba Dharshanam <br>5:40AM</div>
                    <div>Vila Puja <br>6:50AM</div>
                    <div>Sirukala Shanti Puja <br>8:00AM</div>
                    <div>Uchi Kala Puja <br>12:00PM</div>
                    <div>Sayaraksha Puja <br>5:30PM </div>
                    <div>Rakala Puja <br>8:00PM</div>
                </Marquee>
            </div>
        </section>
    </section>
</body>

<style>
    @import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");
    @import url("https://fonts.googleapis.com/css2?family=Indie+Flower&display=swap");
    @import url("https://fonts.googleapis.com/css2?family=The+Nautigal:wght@700&display=swap");
    @import url("https://fonts.googleapis.com/css2?family=Handlee&display=swap");
    @import url("https://fonts.googleapis.com/css2?family=Patrick+Hand+SC&display=swap");
    @import url("https://fonts.googleapis.com/css2?family=Noto+Serif:wght@700&display=swap");
    html {
        background-color: #570100;
        color: #ffd08e;
        font-family: "Roboto", sans-serif;
        overflow: hidden;
    }

    body {
        margin: 0;
        padding: 0;
        /* overflow: hidden !important; */
        height: 95vh;
    }

    #murugan {
        position: relative;
        width: 100%;
        margin-left: auto;
        margin-right: auto;
        padding: 0;
        border: none;
    }

    #bigtitle {
        z-index: 1;
        position: relative; 
        bottom: 12vw; 
        padding-left: 3vw; 
        width: 65%;
        font-size: 8.5vh;
        text-align: left;
        /* font-family: 'Handlee', cursive; */
        /* font-family: 'Patrick Hand SC', cursive; */
        font-family: "Noto Serif", serif;
        transform: scale(0.94);
        animation: scale 5s forwards cubic-bezier(0.5, 1, 0.89, 1);
        /* animation-delay: 1.5s; animation: bgfill 0.5s forwards;  */
    }

    @keyframes scale {
        100% {
            transform: scale(1);
            background-color: rgba(87, 1, 0, 0.75);
        }
    }

    @keyframes bgfill {
        100% {
            background-color: rgba(87, 1, 0, 0.75);
        }
    }

    span {
        display: inline-block;
        opacity: 0;
        filter: blur(2px);
    }

    span:nth-child(1) {
        animation: fade-in 0.8s 0.1s forwards cubic-bezier(0.11, 0, 0.5, 0);
    }

    span:nth-child(2) {
        animation: fade-in 0.8s 0.2s forwards cubic-bezier(0.11, 0, 0.5, 0);
    }

    span:nth-child(3) {
        animation: fade-in 0.8s 0.3s forwards cubic-bezier(0.11, 0, 0.5, 0);
    }

    span:nth-child(4) {
        animation: fade-in 0.8s 0.4s forwards cubic-bezier(0.11, 0, 0.5, 0);
    }

    @keyframes fade-in {
        100% {
            opacity: 1;
            filter: blur(0);
        }
    }

    nav {
        position: fixed;
        font-size: 1.75vw;
        background-color: rgba(87, 1, 0, 0.75);
    }

    nav ul {
        list-style: none;
        color: #ffd08e;
        margin: 10px;
    }

    nav li {
        display: inline;
        float: left;
    }

    nav li a {
        margin: 10px 40px 10px 40px;
    }

    nav a {
        color: #ffd08e;
        text-decoration: none;
    }

    nav {
        top: -1000px;
        animation: downanim 2s 0s forwards;
    }

    @keyframes downanim {
        100% {
            top: 0px;
        }
    }

    @keyframes topanim {
        100% {
            top: 7%;
        }
    }

    li:hover {
        background-color: #ffd08e;
        transition: background-color 0.5s;
    }

    li:hover a {
        color: #570100;
        transition: color 0.5s;
    }

    #posts {
        z-index: 1;
        height: 92%;
        width: 30%;
        position: absolute;
        margin: 0;
        padding: 0;
        top: 100%;
        left: 65%;
        display: flex;
        flex-wrap: wrap;
        flex: none;
        animation: topanim 2s 1s forwards;
        padding-top: 2vh; 
        margin-top: 2vh; 
    }

    #construction {
        width: 100%;
        background-color: #ffd08e;
        color: #722620;
        padding: 0;
        margin-bottom: 4%;
        border: solid #ffd08e 5px;
        border-radius: 20px;
    }

    #construction h2 {
        font-family: "Noto Serif", serif;
        font-size: 2vw;
        margin: 0;
        padding-left: 4%;
    }

    #construction p {
        font-size: 0.75vw;
        padding-left: 4%;
    }

    #events {
        width: 47%;
        background-color: #722620;
        color: #ffd08e;
        /* background-color: #FFD08E;  
  color: #722620; */
        padding: 0;
        margin-bottom: 4%;
        margin-right: 2%;
        border: solid #722620 5px;
        /* border: solid #FFD08E 5px; */
        border-radius: 20px;
        overflow: hidden;
        position: relative;
        height: 29%;
    }

    .marqueeb {
        overflow: hidden;
        position: relative;
        height: 80%;
        margin: 10px 10px 10px 10px;
        background-color: #ffd08e;
        color: #722620;
        border-radius: 20px;
    }

    #events h2 {
        font-family: "Noto Serif", serif;
        font-size: 2vw;
        margin: 0;
        padding-left: 4%;
    }

    #events p {
        font-size: 0.75vw;
        padding-left: 4%;
    }

    #dpujas {
        /* width: 46%;
        background-color: #ffd08e;
        color: #722620;
        padding: 0;
        margin-bottom: 4%;
        border: solid #ffd08e 5px;
        border-radius: 20px;
        height: 29%; */

        width: 47%;
        background-color: #ffd08e;
        color: #722620;
        /* background-color: #FFD08E;  
  color: #722620; */
        padding: 0;
        margin-bottom: 4%;
        margin-right: 2%;
        border: solid #ffd08e 5px;
        /* border: solid #FFD08E 5px; */
        border-radius: 20px;
        overflow: hidden;
        position: relative;
        height: 29%;
    }

    #dpujas h2 {
        font-family: "Noto Serif", serif;
        font-size: 2vw;
        margin: 0;
        padding-left: 4%;
    }

    #dpujas p {
        font-size: 0.75vw;
        padding-left: 4%;
    }

    #donors {
        /* width: 100%;
        background-color: #722620;
        color: #ffd08e;
        padding: 0;
        margin-bottom: 4%;
        border: solid #722620 5px;
        border-radius: 20px;
        height: 35%; */

        width: 100%;
        background-color: #722620;
        color: #ffd08e;
        /* background-color: #FFD08E;  
  color: #722620; */
        padding: 0;
        margin-right: 2%;
        border: solid #722620 5px;
        /* border: solid #FFD08E 5px; */
        border-radius: 20px;
        overflow: hidden;
        position: relative;
        height: 29%;
    }

    #donors h2 {
        font-family: "Noto Serif", serif;
        font-size: 2vw;
        margin: 0;
        padding-left: 4%;
    }

    #donors p {
        font-size: 0.75vw;
        padding-left: 4%;
    }

    .marquee {
        position: relative;
        box-sizing: border-box;
        padding-right: 4%;
        animation: marquee var(--duration,10s) linear infinite;
        z-index: 2;
        display: inline-block;
    }

    .marquee:hover {
        animation-play-state: paused;
    }

    @keyframes marquee {
        0% {
            top: 20em;
        }
        100% {
            top: -20em;
        }
    }

    @keyframes fmarquee {
        0% {
            top: 10em;
        }
        100% {
            top: -10em;
        }
    }

    #donors .marquee {
        position: relative;
        box-sizing: border-box;
        padding-right: 4%;
        z-index: 2;
    }
    #phone { 
        display: none; 
    }
</style>

<MediaQuery query="(max-width: 1280px)" let:matches>
    {#if matches}
        <style>
            body { 
                overflow-x: hidden !important;
                width: 100vw !important;
                height: 100vh !important;
            }
            img { 
                max-width: none;
            }
            #murugan { 
                width: 190vw !important; 
                left: -8vw; 
            }
            #phonebye { 
                display: none;
            }
            #bigtitle { 
                width: 100vw !important; 
                padding-bottom: 0 !important; margin-bottom: 0 !important; 
            }
            #posts {
                position: relative !important;
                left: 0 !important; 
                top: 0 !important; 
                display: flex !important;
                flex-direction: row !important;
                width: 100vw !important; 
                margin-top: -5vh !important; 
            }
            #construction p { 
                font-size: 2vh !important; 
            }
            h1 { 
                font-size: 5vh !important; 
            }
            h2 { 
                font-size: 4vh !important; 
            }
            #donors { 
                margin-right: 0 !important; 
                margin-bottom: 2vh; 
                padding-left: 1.5vw !important; 
            }
            #donors h2 { 
                padding: 0 !important; 
            }
            #dpujas { 
                margin-right: -2% !important; 
                right: 0; 
            }
            #events { 
                margin-right: 6% !important; 
            }
            #phone { 
                display: flex !important; 
            }
            #murugan { 
                margin-top: 10vh !important; 
            }
        </style>
    {/if}
</MediaQuery>
