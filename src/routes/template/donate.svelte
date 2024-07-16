<script>
    import MediaQuery from "../MediaQuery.svelte";
</script>

<MediaQuery query="(max-width: 1280px)" let:matches>
    {#if matches}
        <style>
            .donate { 
                flex-direction: column !important; 
            }
            #online { 
                width: 100% !important; 
            }
            .desc { 
                width: 100% !important; 
            }
            #expl { 
                width: 100% !important; 
            }
        </style>
    {/if}
</MediaQuery>


<div class="donate">
    <slot />
    <div id="expl">
        <h1>Donation for Temple Construction</h1>
        <p style="font-size: 3vh;">
            Your donation, regardless of size, is helpful in the construction of
            the temple. Donors are encouraged to explore the donation options
            below, and are more than welcome to contribute in any way.
        </p>
        <h2>Sponsor a Worker</h2>
        <p class="desc">
            In order to maintain the elegance of our Sanathana Dharma through a
            permanent home for Shanmukar, temple administrators have made
            efforts to work with experienced architects and builders. Sponsors
            are encouraged to contribute towards new workers to build the temple
            at an even quicker pace. Money contributed towards workers will be
            used for the workers' food as well.
        </p>
        <h2>Sponsor Materials</h2>
        <p class="desc">
            The traditional construction of the temple includes the use of
            elegantly carved granite stones. While the granite temple will be
            built to stand thousands of years, it is challenging to cut through.
            Sponsors are encouraged to contribute towards materials, such as:
            granite stones, construction sand, construction tools, etc. For more
            detailed information, please contact temple administration.
        </p>
    </div>
    <div id="vline"></div>
    <div id="online">
        <h1 style="line-height: 7vh;">Donations</h1>
        <p style="font-size: 2vh;">
            Devotees from around the world are urged to donate. Your donation,
            regardless of size, preserves our culture of Sanathana Dharma
            through Shanmukar and will be appropriately allocated towards temple
            construction efforts.
        </p>
        <p style="font-size: 3vh;">Contact for Donation:</p>
        <p style="font-size: 3vh;">Mobile: 0775002162</p>
        <p style="font-size: 3vh; margin-bottom: 5vh;">Mobile: 0770873177</p>
        <h1>Inquiries</h1>
        <p style="font-size: 2vh;">
            Please send any inquiries about donations, or any general inquiries
            about the temple and future events to:
        </p>
        <p style="font-size: 3vh;">info@kandavanam.com</p>
    </div>
</div>

<style>
    * {
        line-height: inherit; 
    }
    h1 {
        padding: 0;
        margin: 0;
        font-size: 7vh;
        margin: 2vh 0vw;
        line-height: 7vh; 
    }
    p {
        margin: 1vh 0vw;
        line-height: 3.25vh; 
    }
    #expl {
        width: 60%;
    }
    .donate {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        width: 80%;
    }
    h2 {
        padding: 0;
        margin: 0;
        padding-top: 2vh;
        font-size: 4vh;
        line-height: 5vh; 
    }
    #vline {
        border-left: 0.5vw solid #ffd08e;
        border-radius: 3vw;
        margin: 2vw;
    }
    #online {
        width: 30%;
    }
    .desc {
        width: 80%;
    }
</style>
