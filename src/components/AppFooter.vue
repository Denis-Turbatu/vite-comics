<script>
export default {
    data() {
        return {
            links: [
                {
                    img: "facebook",
                },
                {
                    img: "twitter",
                },
                {
                    img: "youtube",
                },
                {
                    img: "pinterest",
                },
                {
                    img: "periscope",
                },
            ]
        }
    },
    methods: {
    imgPath(item) {
        return new URL(`../assets/img/footer-${item.img}.png`, import.meta.url).href;
    },
    }
}
</script>

<template>
    <footer>
        <div class="link">

        </div>

        <div class="social">
            <div class="container">
                <a href="#" class="sign-up">SIGN-UP  NOW!</a>
                <div class="social-links">
                    <span>FOLLOW US</span>
                    <a
                        href=""
                        v-for="item in links"
                    >
                        <img :src="imgPath(item)" alt="">
                    </a>
                </div>
            </div>
        </div>
    </footer>
</template>

<style lang="scss">
    @use "../style/partials/mixin" as *;
    @use "../style/partials/variables" as *;

    footer{
        background-color: $grey-color;
        
        .social{
            padding: 40px;
            .container{
                @include container(1280px, auto);
                @include flex(row, space-between, center);

                .sign-up{
                    color: $white-color;
                    font-weight: 600;
                    font-size: 1.2rem;
                    border: solid 3px $blue-color;
                    padding: 10px;
                    text-decoration: none;
                }

                .social-links{
                    @include flex(row, center, center);
                    gap: 10px;

                    span{
                        color: $blue-color;
                        font-weight: 600;
                        font-size: 1.5rem;
                        margin-right: 20px;
                    }
                }

                
            }
        }
    }
</style>