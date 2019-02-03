<template>
    <li class="projects-list__list-item">
        <div class="projects-list__list-item_divider" :style="{ backgroundColor: project.dividerColor }"></div>

        <div class="projects-list__list-item__content">
            <div class="projects-list__list-item__content__title">
                <p>{{project.title}}</p>
            </div>

            <div class="projects-list__list-item__content__content-container">
                <p v-html="project.text"></p>
            </div>

            <div class="projects-list__list-item__content__button-container">
                <button :style="{ backgroundColor: project.dividerColor }" @click="openDetailsPage">Prodrobnosti projekta</button>
            </div>
        </div>
    </li>
</template>

<script>
    import { EventBus } from "../helpers/EventBus";

    export default {
        name: 'ListOfProjects',
        props: {
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
        justify-content: end;
    }

    .projects-list__list-item__content {
        width: 40%;
        margin: 32px;
    }

    .projects-list__list-item__content__title {
        padding: 16px 32px;

        border: 1px solid;

        text-transform: uppercase;

        color: var(--main-text-color);
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
        background-color: var(--main-bg-color);
        border: none;

        padding: 16px 24px;

        text-transform: uppercase;
        
        cursor: pointer;
    }
</style>