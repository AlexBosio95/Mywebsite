<template>
<div class="skills">
    <div class="container py-5" id="skill">
        <h1 class="text-center">Skills</h1>
        <div class="row row-cols-2 row-cols-md-4 row-cols-lg-5 g-3 mt-3">
            <Card v-scrollanimation v-for="card in dataCard" :key="dataCard.id" 
            :title = 'card.title'
            :imgUrl = 'card.imgUrl'
            :type = 'card.type'
            :certification = 'card.certification'
            />
        </div>
    </div>
</div>
</template>

<script>
import Card from './Card.vue'
export default {
    components: { Card },
    data: function(){
        return{
            dataCard: [
                {
                    id: 0,
                    title: 'PHP',
                    type: 'Language',
                    imgUrl: 'php.png',
                    certification: 'Boolean s.r.l.'
                },

                {
                    id: 1,
                    title: 'JavaScript',
                    type: 'Language',
                    imgUrl: 'js.png',
                    certification: 'Boolean s.r.l.'
                },

                {
                    id: 2,
                    title: 'HTML',
                    type: 'Language',
                    imgUrl: 'html.png',
                    certification: 'Boolean s.r.l.'
                },

                {
                    id: 3,
                    title: 'CSS',
                    type: 'Language',
                    imgUrl: 'css.png',
                    certification: 'Boolean s.r.l.'
                },

                {
                    id: 4,
                    title: 'MySQL',
                    type: 'Language',
                    imgUrl: 'mysql.png',
                    certification: 'Boolean s.r.l.'
                },

                {
                    id: 5,
                    title: 'Scss',
                    type: 'Language',
                    imgUrl: 'scss.png',
                    certification: 'Boolean s.r.l.'
                },

                {
                    id: 6,
                    title: 'Vue',
                    type: 'Framework',
                    imgUrl: 'vue.png',
                    certification: 'Boolean s.r.l.'
                },

                {
                    id: 7,
                    title: 'Laravel',
                    type: 'Framework',
                    imgUrl: 'laravel.png',
                    certification: 'Boolean s.r.l.'
                },

                {
                    id: 8,
                    title: 'Bootstrap',
                    type: 'Library',
                    imgUrl: 'bootstrap.png',
                    certification: 'Boolean s.r.l.'
                },

                {
                    id: 9,
                    title: 'VS Code',
                    type: 'IDE',
                    imgUrl: 'vs-code.png',
                    certification: 'Boolean s.r.l.'
                },

                // {
                //     id: 10,
                //     title: 'Python',
                //     type: 'Language',
                //     imgUrl: 'python.png',
                //     certification: 'Udemy'
                // }
            ]
        }
    }

}
</script>

<style scoped lang="scss">

.skills{
    background-color: #252734;

    .more{
        text-align: center;
        cursor: pointer;
        border-radius: 1rem;

        &:hover{
            transform: scale(1.15);
            transition: 0.5s;
        }
    }
}

    .before-enter{
        opacity: 0;
        transform: translateY(50px);
        transition: all 2s ease-out;
    }

    .enter{
        opacity: 1;
        transform: translateY(0px);
    }


</style>