<template>
    <div>
        <div class="sm-menu d-md-none d-sm-block">
            <i v-show="!isVisible" @click="$emit('changeVisible', changeVisibity)" class="fa-solid fa-bars"></i>
        </div>

        <div class="big-menu d-none d-md-block">
            <ul>
                <li v-for="(item, index) in dataMenu" :key="index" :class="{'active' : item.active}">{{item.text}}</li>
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
            }
        }

        .arrow-up:hover{
            transform: translate(0, -0.3rem);
            transition: 0.5s;
        }


    .open{
        padding-top: 1rem;
        background-color: rgb(29, 29, 29);
        border-radius: 0 0 1.5rem 1.5rem;
        animation-name: down;
        animation-duration: 1s;
    }

    .active{
        color: goldenrod;
    }

</style>