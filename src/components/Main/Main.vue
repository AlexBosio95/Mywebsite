<template>
<main>
    <TitleSection />
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
    }

}
</script>

<style scoped lang="scss">

main{
    color: white;
    width: 100%;
    background-color: black;
    overflow-x: hidden;
}

</style>