<template>
    <ul class="projects-list">
        <ProjectCard v-for="(project, index) in projects" :index="index + 1" :project="project"></ProjectCard>
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
                    colorClass: 'dark-text',
                    title: 'Identiteta skupine',
                    text: 'Kaj je identiteta naše skupine? Kako bi se predstavili ljudem?',
                    component: 'Homework1'
                },
                {
                    dividerColor: '#90ADA8',
                    colorClass: 'dark-text',
                    title: 'Tipografija',
                    text: 'Pisava niso samo črke. Tudi iz oblik v naravi lahko ustvarimo sporočilo. Kakšne oblike bi izbrali?',
                    component: 'Homework2'
                },
                {
                    dividerColor: '#54469E',
                    colorClass: 'light-text',
                    title: 'Piktogrami',
                    text: 'Kako bi z uporabo slikovnih elementov predstavili nek pojem?',
                    component: 'Homework3'
                },
                {
                    dividerColor: '#833B22',
                    colorClass: 'light-text',
                    title: 'Plakat, transparent, vabilo',
                    text: 'Kako bi pritegnili pozornost ljudi z nekim elementom v prostoru, naj bo to plakat, grafit ali kaj drugega?',
                    component: 'Homework4'
                },
                {
                    dividerColor: '#eeeeee',
                    colorClass: 'dark-text',
                    title: 'Poster za film',
                    text: 'Ustvarjanje posterjev za filme ni preprosta naloga. Kako bi za izbran film oblikovali nov poster?',
                    component: 'Homework5'
                },
                {
                    dividerColor: '#C26180',
                    colorClass: 'light-text',
                    title: 'Embalaža',
                    text: 'Vsako leto odvržemo na tone embalaže. Kako embalažo bi ustvarili, da bi jo lahko ponovno uporabili?',
                    component: 'Homework6'
                },
                {
                    dividerColor: '#CDA243',
                    colorClass: 'dark-text',
                    title: 'Knjiga',
                    text: 'Oblikovanje knjige je dolg in zapleten proces. Kaj vse je treba upoštevati preden knjiga sploh pride na police?',
                    component: 'Homework7'
                },
                {
                    dividerColor: '#8E2823',
                    colorClass: 'light-text',
                    title: 'Plakat Miltona Glaserja',
                    text: 'Za razstavo svojih del v Mednarodnem grafičnem likovnem centru v Ljubljani je Milton Glaser ustvaril plakat. Kako bi ga lahko izboljšali?',
                    component: 'Homework8'
                },
                {
                    dividerColor: '#5A8152',
                    colorClass: 'light-text',
                    title: 'Kažipot',
                    text: 'Zemljevidi in kažipoti so odličen način za orientacijo v prostoru. Kam bi ga bilo smiselno dodati in kako bi to naredili?',
                    component: 'Homework9'
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