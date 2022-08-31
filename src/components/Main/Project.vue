<template>
<div class="project">
    <div class="row row-cols-1 row-cols-md-2">
        <div class="col">
            <div class="git-card" v-scrollanimation>
                <div class="text-center">
                    <img src="@/assets/img/github.png" alt="github">
                    <h3>{{getNameProfile(myGit.login)}}</h3>
                    <a :href="myGit.html_url">View Profile</a>
                </div>
            </div>
        </div>
        <div class="col">
            <div class="container">
                <div class="git-repo">
                    <h1>My github</h1>
                    <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ex incidunt nulla, vitae nihil vero velit deserunt laudantium illo quo eveniet maxime voluptatem at in reiciendis unde iste ab repudiandae nobis.</p>
                    <div class="repo-container">
                        <h1 class="number-repo">{{counuter}}</h1>
                        <span>Repositories</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>

export default {
    
    data: function() {
        return {
            counuter : 0
        }
    },

    props:{
        myGit: Object,
        myGitRepo: Array,
    },
    methods:{
        getNameProfile(curretIndex){
            if (curretIndex == null) {
                return 'Name Error'
            } else {
                return curretIndex
            }
        },

        getRepoNumber(){
            if (this.myGit.public_repos == null) {
                return 0
            } else {
                return this.myGit.public_repos
            }
        },

        handleScroll () {

            this.getRepoNumber()

            setTimeout(() => {

                setInterval(() => {

                    if (this.counuter <= this.myGit.public_repos) {
                        this.counuter++
                    }

                }, 2000)

                clearInterval()
            
            }, 1000)
            

        }
    },
    created () {
    window.addEventListener('scroll', this.handleScroll);
    },
    destroyed () {
    window.removeEventListener('scroll', this.handleScroll);
    },

}
</script>

<style scoped lang="scss">

.project{
    background-color: #323546;
    padding: 2rem 0;

    .git-card{
        background-color: #252734;
        width: 100%;
        height: 25rem;
        border-radius: 0 2rem 2rem 0;
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;

        img{
            height: 6rem;
            margin: 1rem;
        }

        a{
            color: white;
            background-color: #ffaf2a;
            padding: 0.5rem 1rem;
            text-decoration: none;
            border-radius: 0.3rem;
            display: inline-block;
            margin-top: 1rem;
            text-transform: uppercase;
            font-weight: bold;
            cursor: pointer;

            &:hover{
                transform: scale(1.05);
                transition: 0.5s;
            }
        }

    }

    .git-repo{
        position: relative;
        height: 25rem;

        .repo-container{
            position: absolute;
            bottom: 0;
            left: 0;
            display: flex;
            align-items: center;

            h1{
                font-size: 4rem;
                color: #ffaf2a;
                margin: 0;
                
            }

            span{
                margin: 0.5rem;
            }
        }
    }
}


    .before-enter{
        opacity: 0;
        transform: translatex(-20px);
        transition: all 3s ease-out;
    }

    .enter{
        opacity: 1;
        transform: translatex(0px);
    }

    @media all and (max-width: 500px) {

        .project{
            .git-card{
                border-radius: 0 0;
                width: 90%;
                margin: auto;
            }

            .git-repo{
                width: 90%;
                margin: 1.5rem auto;
                text-align: center;
                display: flex;
                justify-content: center;
                align-items: center;
                flex-wrap: wrap;

                .repo-container{
                    position: relative;
                    display: flex;
                    flex-wrap: wrap;
                    align-items: center;
                    justify-content: center;

                    h1{
                        display: inline-block;
                        width: 100%;
                    }

                }
            }

        }

        .before-enter{
        opacity: 0;
        transform: translateY(-20px);
        transform: translateX(0px);
        transition: all 2s ease-out;
        }

        .enter{
        opacity: 1;
        transform: translateY(0px);
        }

    }

</style>