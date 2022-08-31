<template>
    <div class="col">
        <div :title="title" class="ms_card p-3">
            <div class="description">
                <img :src="require(`@/assets/img/${imgUrl}`)" :alt="title">
                <h2>{{title}}</h2>
                <h6 class="opacity-50">{{type}}</h6>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    props:{
        title : String,
        type : String,
        certification: String,
        imgUrl : String,
    }

    }
</script>

<style scoped lang="scss">

.ms_card{
    text-align: center;
    cursor: pointer;
    border-radius: 0.5rem;
    background-color: #323546;
    position: relative;
    overflow: hidden;

    .description{
        padding-bottom: 5rem;
        position: relative;

        img{
            height: 4rem;
            margin: 0.7rem;
        }
    }

    &:hover{
        transform: translate(0, -0.5rem);
        transition: 0.5s ease-in-out;
        background-color: rgb(29, 29, 29);
    }
}

.ms_card::before{
    content: attr(title);
    color: #252734;
    position: absolute;
    font-size: 5rem;
    font-weight: bold;
    opacity: 0.3;
    bottom: 60px;
    left: 50%;
    margin: 0;
    transform: rotate(-10deg) translate(-50%);
    text-align: center;
}

</style>