<template>
    <ul class="projects-list">
        <ProjectCard v-for="project in projects" :project="project"></ProjectCard>
    </ul>
</template>

<script>
    import ProjectCard from '../components/ProjectCard';
    
    export default {
        name: 'ListOfProjects',
        data() {
            const projects = [
                {
                    dividerColor: '#9198CE',
                    title: 'Identiteta skupine',
                    text: 'Za prvo nalogo smo ustvarili identiteto naše skupine.',
                    component: 'Homework1'
                },
                {
                    dividerColor: '#90ADA8',
                    title: 'Tipografija',
                    text: 'Pri drugi nalogi smo na nek nov način predstavili tip tipografije.'
                },
                {
                    dividerColor: '#54469E',
                    title: 'Piktogrami',
                    text: 'Imeli smo nalogo ustvariti piktograme, slikovne elemente, ki naj bi zelo jasno prikazali izbrane pojme.'
                },
                {
                    dividerColor: '#833B22',
                    title: 'Plakat',
                    text: 'Plakat je kljub zmanjšanem vplivu še vedno močno zastopan.'
                },
                {
                    dividerColor: '#eeeeee',
                    title: 'Poster za film',
                    text: 'Za film "Majhna bela laž" smo ustvarili nov poster.'
                },
                {
                    dividerColor: '#C26180',
                    title: 'Embalaža',
                    text: 'Vsako leto odvržemo na tone embalaže. Kako bi ustvarili tako, da bi jo lahko ponovno uporabili?'
                },
                {
                    dividerColor: '#CDA243',
                    title: 'Knjiga',
                    text: 'Ukvarjali smo se s celotnim procesom oblikovanja knjige, od črk do platnic.'
                },
                {
                    dividerColor: '#8E2823',
                    title: 'Plakati Miltona Glaserja',
                    text: 'Za razstavo svojih del v Mednarodnem grafičnem likovnem centru v Ljubljani je Milton Glaser ustvaril plakat. Kako bi ga lahko izboljšali?'
                },
                {
                    dividerColor: '#5A8152',
                    title: 'Kažipot',
                    text: 'Za zadnjo nalogo smo si morali izbrali neko pot ali stavbo in ustvariti kažipot, ki bo jasen in razumljiv vsem ljudem.'
                }
            ];

            return {
                projects
            };
        },
        components: {
            ProjectCard
        }
    }
</script>

<style scoped>
    .projects-list {
        display: flex;
        flex-direction: column;

        list-style-type: none;

        padding: 0;
        margin: 0;
        
        max-width: 1100px;
    }
</style>