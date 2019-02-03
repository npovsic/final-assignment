<template>
    <main class="parallax-parent">
        <div class="hero-banner parallax-container">
            <h1 class="title major-mono-font center dark-text">Zaključna naloga</h1>
            <h2 class="thin major-mono-font dark-text">pri predmetu oblikovanje vizualnih komunikacij</h2>
        </div>
        
        <div class="list-wrapper content-container">
            <div class="list-wrapper__padding-block"></div>
            
            <ListOfProjects></ListOfProjects>
        </div>

        <footer>
            <p class="major-mono-font right">nejc povšič, 2019</p>
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
        display: flex;
        position: relative;
        z-index: 1;
        background: var(--main-background-color);
        width: 100%;
        flex-direction: column;
        align-items: center;
    }
</style>