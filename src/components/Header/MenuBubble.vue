<template>
<div>
    <a :href="link">
        <div class="menu-circle">
            <i :class="logo"></i>
        </div>
    </a>
</div>

</template>

<script>
export default {
    props: {
        text: String,
        logo: String,
        link: String,
    },
    methods:{
        getFirstChart(string){
            return (string.charAt(0))
        }
    }

}
</script>

<style scoped lang="scss">

    .menu-circle{
        height: 2.5rem;
        width: 2.5rem;
        border-radius: 50%;
        color: white;
        margin: 0.5rem;
        cursor: pointer;
        position: relative;
        background-color: #5c5d5d;

        i{
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);

        }
            &:hover{
                transform: scale(1.08);
                transition: 0.5s;
            }
    }

</style>