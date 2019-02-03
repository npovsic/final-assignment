<template>
    <div id="#app">
        <DetailsPage v-if="showDetails" :detailsData="detailsData"></DetailsPage>

        <LandingPage></LandingPage>
    </div>
</template>

<script>
    import LandingPage from './pages/LandingPage';
    import DetailsPage from './pages/DetailsPage';

    import { EventBus } from "./helpers/EventBus";

    export default {
        name: 'App',
        components: {
            LandingPage,
            DetailsPage
        },
        data() {
            return {
                showDetails: false,
                detailsData: null
            }
        },
        mounted() {
            const vm = this;

            EventBus.$on('openDetails', function (data) {
                vm.showDetails = true;
                vm.detailsData = data;
            });

            EventBus.$on('closeDetails', function () {
                vm.showDetails = false;
                vm.detailsData = null;
            });
        }
    }
</script>

<style>
    :root {
        --main-background-color: #111;
        --main-text-color: #eee;
        --secondary-text-color: #ccc;
    }

    * {
        box-sizing: border-box;
    }

    html, body {
        font-family: 'Roboto', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;

        width: 100%;
        height: 100%;

        margin: 0;
        padding: 0;
    }

    body {
        display: flex;
        flex-direction: column;

        background-color: var(--main-background-color);
        
        color: var(--main-text-color);
    }

    .major-mono-font {
        font-family: 'Major Mono Display', monospace;
    }

    .center {
        text-align: center;
    }
    
    .right {
        text-align: right;
    }

    .normal {
        font-weight: normal;
    }

    .thin {
        font-weight: 300;
    }

    .bold {
        font-weight: bold;
    }

    .dark-text {
        color: var(--main-background-color)
    }

    .uppercase {
        text-transform: uppercase;
    }

    .lowercase {
        text-transform: lowercase;
    }
    
    /* Animations */
    @keyframes slide-up-animation {
        from {
            transform: translateY(100%);
        }

        to {
            transform: translateY(0);
        }
    }

    .slide-up {
        animation-name: slide-up-animation;
        animation-duration: 0.5s;
        animation-iteration-count: 1;
        animation-timing-function: ease;
        animation-fill-mode: forwards;
    }
    
    @keyframes slide-down-animation {
        from {
            transform: translateY(0);
        }

        to {
            transform: translateY(100%);
        }
    }

    .slide-down {
        animation-name: slide-down-animation;
        animation-duration: 0.5s;
        animation-iteration-count: 1;
        animation-timing-function: ease;
        animation-fill-mode: forwards;
    }
</style>
