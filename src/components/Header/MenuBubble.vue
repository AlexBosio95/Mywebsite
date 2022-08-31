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
        height: 3.4rem;
        width: 3.4rem;
        border-radius: 50%;
        color: white;
        margin: 0.5rem;
        cursor: pointer;
        position: relative;
        background-color: #323546;

        i{
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 1.5rem;

        }
            &:hover{
                transform: scale(1.08);
                transition: 0.5s;
            }
    }

</style>