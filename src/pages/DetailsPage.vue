<template>
    <div ref="pageWrapper" class="page-wrapper slide-up">
        <div class="details-page">
            <div class="details-page__container">
                <nav class="details-page__container__title-wrapper" :style="{ borderColor: detailsData.dividerColor }">
                    <h1 class="details-page__container__title-wrapper__title monospace-font">{{detailsData.title}}</h1>

                    <button @click="closeDetailsPage">
                        <i class="material-icons">close</i>
                    </button>
                </nav>
                
                <div class="details-page__container__content-wrapper">
                    <component :is="detailsData.component"></component>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import { EventBus } from "../helpers/EventBus";
    
    import Homework1 from './detailsTemplates/Homework1';
    import Homework2 from './detailsTemplates/Homework2';
    import Homework3 from './detailsTemplates/Homework3';
    import Homework4 from './detailsTemplates/Homework4';
    import Homework5 from './detailsTemplates/Homework5';
    import Homework6 from './detailsTemplates/Homework6';
    import Homework7 from './detailsTemplates/Homework7';
    import Homework8 from './detailsTemplates/Homework8';
    import Homework9 from './detailsTemplates/Homework9';

    export default {
        name: 'DetailsPage',
        components: {
            Homework1,
            Homework2,
            Homework3,
            Homework4,
            Homework5,
            Homework6,
            Homework7,
            Homework8,
            Homework9
        },
        props: {
            detailsData: Object
        },
        data() {
            return {};
        },
        mounted() {
            EventBus.$on('triggerCloseAnimation', this.closeDetailsPage);
        },
        methods: {
            closeDetailsPage() {
                const pageWrapperEl = this.$refs['pageWrapper'];

                pageWrapperEl.classList.add('slide-down');

                ['webkitAnimationEnd', 'oAnimationEnd', 'msAnimationEnd', 'animationend'].forEach((eventType) => {
                    pageWrapperEl.addEventListener(eventType, function () {
                        EventBus.$emit('closeDetails');
                    });
                });
                
            }
        }
    }
</script>

<style scoped>
    .page-wrapper {
        position: fixed;
        width: 100vw;
        height: 100vh;

        z-index: 1;
    }
    
    .details-page {
        width: 100%;
        height: 100%;

        background-color: var(--main-background-color);
        
        display: flex;
        
        flex-direction: column;
    }
    
    .details-page__container {
        flex: 1;
        
        overflow-y: auto;
    }
    
    .details-page__container__title-wrapper {
        position: relative;
        margin: 0 16px;
        border-bottom: 2px solid;
    }
    
    .details-page__container__title-wrapper__title {
        margin: 8px;
        padding: 32px;

        font-size: 24px;
    }

    button {
        height: 100%;
        width: 64px;
        background: transparent;
        border: none;
        cursor: pointer;
        position: absolute;
        top: 0;
        right: 0;
    }

    button > i {
        font-size: 32px;

        color: var(--main-text-color);
    }


    .details-page__container__content-wrapper {
        flex: 1;

        padding: 32px;

        max-width: 60%;

        margin: 0 auto;
    }
</style>