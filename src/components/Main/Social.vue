<template>
    <div class="social" v-scrollanimation>
        <a href="https://www.instagram.com/alexbosio95/?hl=it" target="_blank"><i class="fa-brands fa-instagram"></i></a>
        <a href="https://www.linkedin.com/in/alex-bosio-91034aa5" target="_blank"><i class="fa-brands fa-linkedin"></i></a>
        <a href="https://github.com/AlexBosio95" target="_blank"><i class="fa-brands fa-github"></i></a>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>

@import '@/style/variables.scss';

    .social{
        display: flex;
        justify-content: center;
        background-color: $GrayStrong;
        margin: 2rem auto;
        width: 50%;
        border-radius: 0.5rem;

        a{
            color: $White;
            font-size: 1.5rem;
            margin: .5rem;
        }
    }

    // .before-enter{
    //     opacity: 0;
    //     transform: translateY(-40px);
    //     transition: all 1s ease-out;
    // }

    // .enter{
    //     opacity: 1;
    //     transform: translateY(0px);
    // }

    @media all and (min-width: 992px) {

        .social{
            display: flex;
            flex-direction: column;
            align-items: center;
            background-color: $GrayStrong;
            width: 3rem;
            margin: 0;
        }

        // .before-enter{
        //     opacity: 0;
        //     transform: translateX(0px);
        //     transform: translateY(0px);
        //     transition: all 1s ease-out;
        // }

        // .enter{
        //     opacity: 1;
        //     transform: translateX(0px);
        //     transform: translateY(0px);
        // }

    }

</style>