<template>
    <main class="parallax-parent">
        <div class="hero-banner parallax-container">
            <h1 class="title major-mono-font center dark-text uppercase">Zaključna naloga</h1>
            
            <h1 class="thin monospace-font dark-text center subtitle">Pri predmetu oblikovanje vizualnih komunikacij</h1>
            
            <h1 class="thin monospace-font dark-text center subtitle">Nejc Povšič</h1>
        </div>
        
        <div class="list-wrapper content-container">
            <div class="list-wrapper__padding-block"></div>
            
            <h2 class="thin subtitle monospace-font center">Začetek poti</h2>
            
            <ListOfProjects></ListOfProjects>

            <h2 class="thin subtitle monospace-font center">Prišli ste na cilj</h2>
        </div>

        <footer>
            <p class="monospace-font uppercase right">Nejc Povšič, 2019</p>
        </footer>
    </main>
</template>

<script>
    import ListOfProjects from '../components/ListOfProjects';

    export default {
        name: 'LandingPage',
        components: {
            ListOfProjects
        }
    }
</script>

<style>
    main {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    footer {
        margin-top: 64px;
        padding: 32px;
        width: 100%;
        height: 200px;

        color: var(--main-text-color);
        
        border-top: 2px solid #ccc;
    }
    
    .hero-banner {
        width: 100%;
        background-color: #ccc;

        display: flex;
        
        flex-direction: column;

        justify-content: center;
        align-items: center;
    }
    
    .title {
        font-weight: normal;
        
        font-size: 4rem;
        text-transform: uppercase;
    }
    
    .subtitle {
        font-size: 2rem;
        text-transform: uppercase;
    }
    
    .list-wrapper {
        width: 75%;
        margin-top: -58px;
    }
    
    .list-wrapper__padding-block {
        width: 100%;
        height: 64px;
    }

    .parallax-parent {
        perspective: 1px;
        transform-style: preserve-3d;
        height: 100vh;
        overflow-x: hidden;
        overflow-y: scroll;
    }

    .parallax-container {
        display: flex;
        flex: 1 0 auto;
        position: relative;
        transform: translateZ(-1px) scale(2);
        z-index: -1;
        height: 600px;
        transform-origin: 50% 600px;
    }

    .content-container {
        position: relative;
        z-index: 1;
        background: var(--main-background-color);
        width: 100%;

        display: flex;

        display: grid;
        justify-content: center;
    }
</style>