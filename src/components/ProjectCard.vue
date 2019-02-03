<template>
    <li class="projects-list__list-item">
        <div class="projects-list__list-item_divider" :style="{ backgroundColor: project.dividerColor }"></div>

        <div class="projects-list__list-item__content">
            <div class="projects-list__list-item__content__title-wrapper">
                <div class="projects-list__list-item__content__title-wrapper__index" :style="{ backgroundColor: project.dividerColor }">
                    <p :class="project.colorClass">{{index}}</p>
                </div>
                <div class="projects-list__list-item__content__title-wrapper__title">
                    <p>{{project.title}}</p>
                </div>
            </div>

            <div class="projects-list__list-item__content__content-container">
                <p v-html="project.text"></p>
            </div>

            <div class="projects-list__list-item__content__button-container">
                <button :class="project.colorClass" :style="{ backgroundColor: project.dividerColor }" @click="openDetailsPage"><span>Več o nalogi</span></button>
            </div>
        </div>
    </li>
</template>

<script>
    import { EventBus } from "../helpers/EventBus";

    export default {
        name: 'ProjectCard',
        props: {
            index: Number,
            project: Object
        },
        methods: {
            openDetailsPage() {
                EventBus.$emit('openDetails', this.project);
            }
        }
    }
</script>

<style scoped>
    .projects-list__list-item {
        display: flex;

        position: relative;
    }

    .projects-list__list-item_divider {
        height: 100%;
        width: 5px;
        position: absolute;
        top: 0;
        left: 50%;

        border: 1px solid #000;
    }

    .projects-list__list-item:nth-child(even) {
        justify-content: flex-end;
    }

    .projects-list__list-item__content {
        width: 40%;
        margin: 32px;
    }
    
    .projects-list__list-item__content__title-wrapper {
        display: flex;
    }

    .projects-list__list-item__content__title-wrapper__index {
        padding: 16px 32px;

        margin: 0 8px;

        border: 1px solid;

        text-transform: uppercase;

        color: var(--main-text-color);

        order: 2;
    }

    .projects-list__list-item__content__title-wrapper__title {
        padding: 16px 32px;

        border: 1px solid;

        text-transform: uppercase;

        color: var(--main-text-color);

        flex: 1;

        order: 1;
    }


    .projects-list__list-item:nth-child(even) .projects-list__list-item__content__title-wrapper__index {
        order: 1;
    }

    .projects-list__list-item:nth-child(even) .projects-list__list-item__content__title-wrapper__title {
        order: 2;
    }

    .projects-list__list-item__content__content-container {
        color: var(--secondary-text-color);
    }

    .projects-list__list-item__content__button-container {
        display: flex;
        justify-content: start;

        padding: 16px 0;
    }

    .projects-list__list-item:nth-child(even) > .projects-list__list-item__content > .projects-list__list-item__content__button-container {
        justify-content: end;
    }

    button {
        position: relative;
        border: none;
        padding: 16px 24px;
        text-transform: uppercase;
        cursor: pointer;
    }

    button::before {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: auto;

        background: rgba(255, 255, 255, 0.2);

        opacity: 0;
        
        transition: opacity 0.5s ease;
    }

    button:hover::before {
        opacity: 1;
    }
</style>