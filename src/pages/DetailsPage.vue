<template>
    <div ref="pageWrapper" class="page-wrapper slide-up">
        <div class="details-page">
            <div class="details-page__container">
                <div class="details-page__container__title-wrapper" :style="{ borderColor: detailsData.dividerColor }">
                    <h2 class="details-page__container__title-wrapper__title major-mono-font lowercase">{{detailsData.title}}</h2>

                    <button @click="closeDetailsPage">
                        <i class="material-icons">close</i>
                    </button>
                </div>
                
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

    export default {
        name: 'DetailsPage',
        components: {
            Homework1
        },
        props: {
            detailsData: Object
        },
        data() {
            return {};
        },
        mounted() {

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

    nav {
        position: absolute;
        
        width: 100%;
        height: 64px;

        display: flex;
        justify-content: flex-end;
    }

    button {
        height: 100%;
        width: 64px;
        background: transparent;
        border: none;
        cursor: pointer;
    }

    button > i {
        font-size: 32px;

        color: var(--main-text-color);
    }

    .details-page__container {
        flex: 1;
        
        display: flex;
        flex-direction: column;
    }
    
    .details-page__container__title-wrapper {
        margin: 0 16px;
        
        border-bottom: 2px solid;

        display: flex;

        justify-content: space-between;
    }
    
    .details-page__container__title-wrapper__title {
        margin: 8px;
        padding: 32px;
    }

    .details-page__container__content-wrapper {
        flex: 1;

        padding: 32px;
    }
</style>