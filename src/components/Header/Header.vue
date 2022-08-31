<template>
<header :class="{'open' : isVisible}">
    <div class="container-md">
        <div class="row row-cols-2">
            
            <div class="col d-flex align-items-center">
                <Menu 
                :isVisible = 'isVisible'
                :dataMenu = 'dataMenu'
                @changeVisible = 'changeVisibity' />
            </div>

            <div v-if="!isVisible" class="col d-flex justify-content-end align-items-center">
                <h1>logo</h1>
            </div>

            <div class="col-12 w-100 text-center" v-show="isVisible">
                    <div class="menu-container" @click="isVisible = !isVisible">
                        <MenuBubble v-for="(item, index) in dataMenu" :key="index"
                        :text = 'item.text'
                        :logo = 'item.logo'
                        :link = 'item.link'/>
                    </div>
            </div>

            <div class="col-12 w-100 text-center arrow-up mt-2" v-show="isVisible">
                <i @click="isVisible = !isVisible" class="fa-solid fa-chevron-up"></i>
            </div>
        </div>
    </div>

</header>
</template>

<script>
import MenuBubble from './MenuBubble.vue';
import Menu from './Menu.vue';

export default {
    components:{
        MenuBubble,
        Menu,
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
            isVisible: null
        }
    },
    methods:{
        changeVisibity(){
            this.isVisible = !this.isVisible
        }
    }

}
</script>

<style scoped lang="scss">

    header{
        position: fixed;
        background-color: #252734;
        color: white;
        width: 100%;
        z-index: 1;

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
            }
        }

        .arrow-up:hover{
            transform: translate(0, -0.3rem);
            transition: 0.5s;
        }

        .menu-container{
            display: flex;
            justify-content: center;
        }

    }

    .open{
        padding-top: 2rem;
        background-color: rgba(29, 29, 29, 0.5);
        border-radius: 0 0 1rem 1rem;
        animation-name: down;
        animation-duration: 0.4s;
    }



    @keyframes down {
        0%   {top: -8rem;}
        100% {top: 0;}
}


</style>