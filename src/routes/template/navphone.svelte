<script>
    import { fly } from 'svelte/transition';
  
    let showDropdown = false;
  </script>
  
  <style>
    .navphone {
        background-color: #360100;
        padding: 0; margin: 0; 
        height: 12vh; width: 100vw; 
        display: flex;
        align-items: center; 
        justify-content: space-between;
    }
  
    .navphone img {
        padding: 0; margin: 0; 
        object-fit: contain; 
        height: 80%; 
        padding-left: 2vw; 
    }
  
    .navphone p {
        padding: 0; margin: 0; 
        width: 40vw;
        padding-left: 3vw; 
    }
  
    .navphone #menu {
        margin-left: auto; 
        padding-right: 4vw; 
        cursor: pointer; /* Indicates the element can be clicked */
    }
  
    .dropdown-menu {
        position: absolute;
        width: 100%; 
        right: 0;
        top: 100%;
        background-color: #3401005a;
        z-index: 1;
        height: 100vh; 
    }
  
    .dropdown-menu a {
        padding: 3vh 0vw; 
        text-decoration: none;
        display: flex; 
        justify-content: center; 
        border: 1px solid rgba(255, 255, 255, 0.2); 
        background-color: #300100a5;
        border-left: none; border-right: none; 
    }

    #spec { 
        color: #920301;
        background-color: #ffd08ec7;
    }

     p { 
        font-size: 2.5vh; 
     }
     a { 
        text-decoration: none;
     }
     a, a:hover, a:visited, a:active { 
        color: inherit; 
     }
  </style>
  
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <!-- svelte-ignore a11y-no-static-element-interactions -->
  <div class="navphone" on:click={() => showDropdown = !showDropdown}>
      <slot />
      <img src="../favicon.png" alt="logo" />
      <p>Kandavanam Temple</p>
      <img id="menu" src="../menu.webp" alt="menu">
      {#if showDropdown}
        <div class="dropdown-menu" transition:fly="{{ y: -20, duration: 300 }}">
          <a href="/">Home</a>
          <a href="/about">About Us</a>
          <a href="/construction">Temple Construction</a>
          <a href="/donate" id="spec">Donate Today</a>
        </div>
      {/if}
  </div>
  