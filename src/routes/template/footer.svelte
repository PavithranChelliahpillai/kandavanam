<div class="footer">
    <slot />
    <p>info@kanthavanamtemple.com</p>
    <p>© Copyright Kanthavanam Temple</p>
    <p>Developed by <a href="https://www.linkedin.com/in/pavithran-chelliahpillai-356615217/">Pavithran Chelliahpillai</a></p>
</div>

<style>
    .footer { 
        width: 100%; 
        background-color: #360100;
        display: flex; 
        flex-direction: row; 
        margin-top: 2vh; 
        flex-wrap: wrap; 
    }
    .footer p { 
        flex: 1 1 0px; 
        flex-grow: 1; 
        text-align: center; 
        padding: 3vh; 
    }
    .footer a { 
        color: #FFD08E;
        text-decoration:underline;
    }
</style>