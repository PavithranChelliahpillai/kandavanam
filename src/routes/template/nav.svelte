<script>
    /**
     * @type {any}
     */
    let y;
    import MediaQuery from "../MediaQuery.svelte";
    import { fade } from "svelte/transition";
    import { onMount } from "svelte";
    let ready = false;
    onMount(() => (ready = true));

    // When true, the bar sits above the right-hand panel column instead of
    // spanning the full width (used on the home page).
    export let rightAligned = false;
</script>

{#if y > 0}
    <style>
        #home,
        #about,
        #contact,
        #projects {
            background-color: #4502009b;
        }
        #home:hover,
        #about:hover,
        #contact:hover,
        #projects:hover {
            background-color: #ac08037a;
        }
    </style>
{/if}

<nav class="navbar">
    <slot />
    <div id="total" class:right={rightAligned}>
        <div class="elem" id="home" style="padding: 0; border-left: none;">
            <a href="/">Home</a>
        </div>
        <div class="elem" id="about"><a href="/about">About Us</a></div>
        <div class="elem" id="projects">
            <a href="/construction">Temple Construction</a>
        </div>
        <div class="elem" id="donate"><a href="/donate" style="color: #570100;">Donate Today</a></div>
    </div>
</nav>

<svelte:window bind:scrollY={y} />

<!-- <MediaQuery query="(max-width: 480px)" let:matches>
    {#if matches}
        <style>
            .navbar {
                display: none;
            }
            .dispapp p {
                font-size: 2vw !important;
            }
            .dispapp h1 {
                font-size: 3vw !important;
            }
        </style>
    {/if}
</MediaQuery> -->

<style>
    .navbar {
        display: relative;
        z-index: 500;
    }
    /* Rounded translucent panel — shared by every nav bar */
    #total {
        display: flex;
        flex-direction: row;
        margin: 0;
        list-style-type: none;
        position: fixed;
        width: 100%;
        box-sizing: border-box;
        border: 1px solid rgba(255, 208, 142, 0.35);
        border-top: none;
        border-radius: 0 0 18px 18px;
        background: rgba(87, 1, 0, 0.55);
        backdrop-filter: blur(6px);
        -webkit-backdrop-filter: blur(6px);
        box-shadow: 0 6px 18px rgba(0, 0, 0, 0.25);
        padding: 0.5vh 0.6vw;
        gap: 0.4vw;
    }
    /* Home page: anchor the bar above the right-hand panel column */
    #total.right {
        left: 65%;
        width: 30%;
    }
    .elem {
        position: relative;
        flex: 1 1 0px;
        display: flex;
        border-radius: 12px;
        overflow: hidden;
        transition: background 0.3s ease;
    }
    a {
        text-decoration: none;
        color: #ffd08e;
        font-family: "Noto Serif", serif;
        font-size: 2.1vh;
        letter-spacing: 0.02em;
        line-height: 1.25;
        text-align: center;
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 2.2vh 0.4vw;
    }
    /* Home page bar is narrower, keep its links a touch tighter */
    #total.right a {
        padding: 1.4vh 0.4vw;
        font-size: 1.7vh;
    }
    .elem:not(#donate):hover {
        background: rgba(255, 208, 142, 0.14);
    }
    #donate {
        background: #ffd08e;
        border-radius: 12px;
    }
    #donate a {
        font-weight: 700;
    }
    #donate:hover {
        background: #be9254;
    }
</style>
