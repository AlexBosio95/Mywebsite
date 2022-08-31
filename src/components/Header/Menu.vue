<template>
    <div>
        <div class="sm-menu d-md-none d-sm-block">
            <i v-show="!isVisible" @click="$emit('changeVisible', changeVisibity)" class="fa-solid fa-bars"></i>
        </div>

        <div class="big-menu d-none d-md-block">
            <ul>
                <li v-for="(item, index) in dataMenu" :key="index"> <a @click="changeColor(index)" :class="{'active' : item.active}" :href="item.link">{{item.text}}</a></li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        isVisible: Boolean,
        dataMenu: Array,
    },
    methods:{
        changeVisibity(){
            this.isVisible = !this.isVisible
        },
        changeColor(currentindex){

            this.dataMenu.forEach(element => {
                element.active = false
            });

            this.dataMenu[currentindex].active = true

        }
    }

}
</script>

<style scoped lang="scss">


        i{
            font-size: 1.5rem;
            cursor: pointer;
        }

        h1{
            line-height: 8vh; 
        }

        ul{
            list-style: none;
            padding: 0;

            li{
                color: white;
                display: inline;
                margin-right: 1rem;
                cursor: pointer;

                a{
                    color: white;
                    text-decoration: none;
                }
            }
        }

        .arrow-up:hover{
            transform: translate(0, -0.3rem);
            transition: 0.5s;
        }
    

    .active{
        color: goldenrod;
    }

</style>