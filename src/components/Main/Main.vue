<template>
<main>
    <TitleSection id="home"
        :dataMenu= 'dataMenu'/>
    <Skills id="skill"/>
    <Project id="project"
    :myGit = 'myGit'
    :myGitRepo = 'myGitRepo' />
    

</main>
</template>

<script>
import TitleSection from './TitleSection.vue';
import Skills from './Skills.vue';
import Project from './Project.vue';
export default {

    components:{
        TitleSection,
        Skills,
        Project,
    },
    props:{
        myGit: Object,
        myGitRepo: Array,
    }, 
    data: function(){
        return{
            dataMenu:[
                {
                    text: 'Home', 
                    active: true,
                    logo: 'fa-solid fa-house',
                    link: '#home',
                },

                {
                    text: 'Skills', 
                    active: false,
                    logo: 'fa-solid fa-swatchbook',
                    link: '#skill',
                },

                {
                    text: 'Project',
                    active: false,
                    logo: 'fa-solid fa-lines-leaning',
                    link: '#project',
                },

                {
                    text: 'Contact',
                    active: false,
                    logo: 'fa-solid fa-user',
                    link: '#contact',
                }
            ],
        }
    }
}

</script>

<style scoped lang="scss">

@import '@/style/variables.scss';

main{
    color: $White;
    width: 100%;
    background-color: $GrayStrong;
    overflow-x: hidden;
}

</style>