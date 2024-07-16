<div class="footer">
    <slot />
    <p>info@kandavanamtemple.com</p>
    <p>© Copyright Kanthavanam Temple</p>
    <p>Developed by Pavithran Chelliahpillai</p>
</div>

<style>
    .footer { 
        width: 100%; 
        background-color: #360100;
        display: flex; 
        flex-direction: row; 
        margin-top: 2vh; 
    }
    .footer p { 
        flex: 1 1 0px; 
        flex-grow: 1; 
        text-align: center; 
        padding: 3vh; 
    }
</style>