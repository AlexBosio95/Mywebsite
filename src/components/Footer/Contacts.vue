<template>
    <div class="contacts position-reltive">
        <div class="d-flex justify-content-center py-3" v-scrollanimation>
            <div class="position-absolute">
                <i class="fa-brands fa-instagram"></i>
                <i class="fa-brands fa-linkedin"></i>
                <i class="fa-brands fa-github"></i>
            </div>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">

.contacts{
    background-color: #252734;
    height: 6rem;

    i{
        font-size: 2rem;
        color: white;
        margin: 1rem;
        cursor: pointer;
    }

}

.before-enter{
    opacity: 0;
    transform: translateY(60px);
    transition: all 2s ease-out;
}

.enter{
    opacity: 1;
    transform: translateY(0px);
}


</style>