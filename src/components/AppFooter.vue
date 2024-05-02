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
            ],
            comicsLink: [
                {
                    name: "Characters",
                },
                {
                    name: "Comics",
                },
                {
                    name: "Movies",
                },
                {
                    name: "Tv",
                },
                {
                    name: "Games",
                },
                {
                    name: "Videos",
                },
                {
                    name: "News",
                },
            ],
            shopLink: [
                {
                    name: "Shop DC",
                },
                {
                    name: "Shop DC Collectibles",
                },
            ],
            dcLink: [
                {
                    name: "Therm of use",
                },
                {
                    name: "Privacy policy(New)",
                },
                {
                    name: "Ad Choises",
                },
                {
                    name: "Advertising",
                },
                {
                    name: "Jobs",
                },
                {
                    name: "Subscription",
                },
                {
                    name: "Talent Workshop",
                },
                {
                    name: "CPSC Certification",
                },
                {
                    name: "Ratings",
                },
                {
                    name: "Shop Help",
                },
                {
                    name: "Contact Us",
                },
            ],
            sitesLink: [
                {
                    name: "DC",
                },
                {
                    name: "MAD Magazzine",
                },
                {
                    name: "DC Kids",
                },
                {
                    name: "DC Universe",
                },
                {
                    name: "DC Power Visa",
                },
            ],
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
    <div class="footer-banner">
        <div class="container">
            <div class="links-list">
                <div class="col">
                    <span class="title-links">DC COMICS</span>
                    <ul>
                        <li 
                             v-for="item in comicsLink" 
                        >
                            <a href="#" class="item-link">{{ item.name }}</a>
                        </li>
                    </ul>
                    <span class="title-links">SHOP</span>
                    <ul>
                        <li 
                            v-for="item in shopLink"
                        >
                            <a href="#" class="item-link">{{ item.name }}</a> 
                        </li>
                    </ul>
                </div>
                <div class="col">
                    <span class="title-links">DC</span>
                    <ul>
                        <li 
                            v-for="item in dcLink"
                        >
                            <a href="#" class="item-link">{{ item.name }}</a>
                        </li>
                    </ul>
                </div>
                <div class="col">
                    <span class="title-links">SITES</span>
                    <ul>
                        <li 
                            v-for="item in sitesLink"
                        >
                            <a href="#" class="item-link">{{ item.name }}</a>
                        </li>
                    </ul>
                </div>
            </div>
            <img src="../assets/img/dc-logo-bg.png" alt="">
        </div>
    </div>
    <footer>
        <div class="social">
            <div class="container">
                <a href="#" class="sign-up">SIGN-UP  NOW!</a>
                <div class="social-links">
                    <span class="title-links">FOLLOW US</span>
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

    .footer-banner{
        background-color: $jumbo-color;
        .container{
            position: relative;
            @include container(1280px, auto);
            @include flex(row, space-between, center);
            .links-list{
                width: 40%;
                @include flex(row, space-between, start);
                .col{
                    margin: 50px 0;
                    width: calc(100% / 3 - 8px);
                    .title-links{
                        color: $white-color;
                    }

                    ul{
                        list-style-type: none;
                        margin-top: 15px;
                        .item-link{
                            color: $lightgrey-color;
                            font-size: 0.9rem;
                            text-decoration: none;
                        }
                    }
                }
            }
            img{
                position: absolute;
                right: 0;
            }
        }
    }

    footer, .col{
        .title-links{
            color: $blue-color;
            font-weight: 600;
            font-size: 1.5rem;
            margin-right: 20px;
        }
    }

    footer{
        background-color: $grey-color;
        position: relative;
        z-index: 1;
        
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
                }

                
            }
        }
    }
</style>