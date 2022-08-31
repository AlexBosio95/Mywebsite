<template>
<div class="title-section" id="home">
    <div class="container">
        <div class="row row-cols-1 row-cols-md-2 pt-3">
            <div class="col d-flex align-items-center flex-wrap">
                <div>
                    <h3 v-scrollanimation class="animation-opacity">Hi, I'm Alex.</h3>
                    <h1 v-scrollanimation class="animation-opacity">I'm Full Stack Web Developer</h1>
                    <div v-scrollanimation class="bar animation-opacity-md"></div>
                    <p v-scrollanimation class="animation-opacity-md">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Magni est sequi nesciunt omnis, vitae saepe optio fugiat ab, debitis velit qui quos corrupti! Harum ipsam excepturi et, sed dolores eius!</p>
                </div>
            </div>
            <div v-scrollanimation class="col d-flex justify-content-center align-items-end">
                <img class="animation-opacity-md" src="@/assets/img/mypc.png" alt="">
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">

.title-section{
    background-color: #323546;
    
    height: 100vh;
    padding-top: 10vh;

        h1{
            font-size: 6rem;
            font-weight:bold;
        }
    
        .button-down{
            color: goldenrod;
            text-align: center;
            margin: 2rem;
            cursor: pointer;
    
            button{
                color: goldenrod;
                background-color: transparent;
                width: 100%;
                border: none;
            }
        }

        .bar{
            width: 6rem;
            height: 0.2rem;
            background-color: goldenrod;
            margin: 1.5rem 0rem;
        }
    
        img{
            height: 30rem;
        }

}

    .before-enter{
        opacity: 0;
        transform: translateY(40px);
        transition: all 1s ease-out;
    }

    .enter{
        opacity: 1;
        transform: translateY(0px);
    }


    @media all and (max-width: 500px) {

    .title-section{
        height: 100%;

        h1{
            font-size: 4.5rem;
        }
    }


}



</style>