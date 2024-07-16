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

<div class="navbar">
    <slot />
    <div id="total">
        <div class="elem" id="home" style="padding: 0; border-left: none;">
            <a href="/">Home</a>
        </div>
        <div class="elem" id="about"><a href="/about">About Us</a></div>
        <div class="elem" id="projects">
            <a href="/construction">Temple Construction</a>
        </div>
        <div class="elem" id="donate"><a href="/donate" style="color: #570100;">Donate Today</a></div>
    </div>
</div>

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
    #total {
        display: flex;
        flex-direction: row;
        margin: 0;
        padding: 0;
        list-style-type: none;
        position: fixed;
        width: 100%;
    }
    .elem {
        float: left;
        border: 1px solid #ffd08e;
        border-right: 0;
        position: relative;
        flex: 1 1 0px;
        transition: all 0.5s;
        padding: 0vh 0vw; 
    }
    a {
        text-decoration: none;
        color: #ffd08e;
        padding-left: 1vw;
        display: flex;
        padding-top: 2.5vh !important;
        padding-bottom: 2.5vh !important;
        align-items: center;
    }
    .elem:hover {
        background: #25010096;
    }
    #home {
        flex-grow: 2;
    }
    #donate {
        background: #ffd08e;
        flex-grow: 2; 
    }
    #donate:hover { 
        background: #be9254;
    }
</style>
