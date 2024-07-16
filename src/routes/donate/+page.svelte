<script>
    import Navbar from "../template/nav.svelte";
    import Navphone from "../template/navphone.svelte";
    import Donate from "../template/donate.svelte";
    import MediaQuery from "../MediaQuery.svelte";
    import Footer from "../template/footer.svelte"
</script>

<head>
    <title>Donate Today</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Donate to the granite temple construction project.">
    <meta name="keywords" content="HTML, CSS, JavaScript">
    <meta name="author" content="Pavithran Chelliahpillai">
</head>

<body>
    <div id="cont">
    <div id="phonebye" style="position: fixed; top: 0; z-index: 500;">
        <Navbar></Navbar>
    </div>
    <div id="phone" style="position: fixed; top: 0; z-index: 500;">
        <Navphone></Navphone>
    </div>

    <div id="bgp" style="margin-top: 9vh; display: flex; justify-content: center; justify-content: center; position: relative;">
        <Donate></Donate>
    </div>
    </div>
    <Footer></Footer>
</body>

<MediaQuery query="(max-width: 1280px)" let:matches>
    {#if matches}
        <style>
            #phonebye { 
                display: none !important; 
            }
            #phone { 
                display: flex !important; 
            }
            #bgp {
                margin-top: 12vh !important; 
            }
        </style>
    {/if}
</MediaQuery>

<style> 
    * {
        box-sizing: border-box;
    }
    /* body {
        min-height: 100%; 
        position: relative;
    } */
    .footer {
        position: absolute;
        bottom: 0;
        width: 100%;
        /* Additional footer styles */
    }
    body { 
        background-color: #570100;
    }
    div { 
        padding: 0; 
        margin: 0; 
    }
    #phone { 
        display: none; 
    }
    #cont { 
        min-height: 80.6vh; 
    }
</style>
