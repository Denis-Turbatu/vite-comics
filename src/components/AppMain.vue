<script>
import jsonData from "../assets/data/dc-comics.json";

export default {
    data() {
        return {
            comicsItems: [
                {
                    img: `buy-comics-digital-comics.png`,
                    name: "digital comics",
                },
                {
                    img: `buy-comics-merchandise.png`,
                    name: "dc merchandise",
                },
                {
                    img: `buy-comics-subscriptions.png`,
                    name: "subscription",
                },
                {
                    img: `buy-comics-shop-locator.png`,
                    name: "comic shop location",
                },
                {
                    img: `buy-dc-power-visa.svg`,
                    name: "comic shop location",
                },
            ],

            data: jsonData,
        }
    },
    methods: {
    imgPath(item) {
        return new URL(`../assets/img/${item.img}`, import.meta.url).href;
    },
    }
}
</script>

<template>
    <main> 
            <div class="hero-section"> 
                <div class="container">
                    <div class="tag">
                        <span class="blue-tag">CURRENT SERIES</span>
                    </div>
                </div>
            </div>

            <div class="content"> 
                <div class="container">
                    <div class="row">
                        <div class="col" v-for="comic in data">
                            <img :src="`${comic.thumb}`" alt="">
                            <span>{{comic.series}}</span>
                        </div>
                    </div>
                    
                    <a href="#" class="blue-tag">LOAD MORE</a>
                </div>
            </div>

            <div class="comics-section">
                <div class="container">
                    <span
                        class="comics-item"
                        v-for="item in comicsItems"
                    >
                    <img :src="imgPath(item)" alt="">
                    {{ item.name.toUpperCase() }}
                    </span>
                </div> 
            </div>
    </main>
</template>

<style lang="scss">
    @use "../style/partials/mixin" as *;
    @use "../style/partials/variables" as *;
    main{
        background-color: $darkgrey-color;
        color: $white-color;

            .blue-tag{
                margin-top: 15px;
                padding: 15px 25px;
                background-color: $blue-color;
                color: white;
                text-decoration: none;
                font-size: 0.9rem;
            }

            .hero-section{
                height: 500px;
                background-image: url("../assets/img/jumbotron.jpg");
                background-size: cover;
                position: relative;
                .container{
                    @include container(1280px, auto);

                    .tag{
                        position: absolute;
                        bottom: 0;
                        transform: translateY(50%);
                        font-weight: 600;
                        font-size: 1.1rem;
                    }
                }
            }

            .content{
                font-size: 1.6rem;
                font-weight: 600;
                padding: 50px 0;
                .container{
                    @include container(1280px, auto);
                    @include flex(column, center, center);

                    .row{
                        @include container(1280px, auto);
                        @include flex(row, space-between, start);
                        flex-wrap: wrap;
                        .col{ 
                            width: calc(100% / 6 - 20px);
                            img{
                                height: 170px;
                                width: 170px;
                            }

                            span{
                                font-size: 0.9rem;
                            }
                        }
                    }
                }
            }
            .comics-section{
                background-color: $blue-color;
                padding: 70px 0;
                position: relative;
                z-index: 1;
                .container{
                    @include container(1280px, auto);
                    @include flex(row, center, center);
                    gap: 10px;

                    img{
                        max-width: 50px;
                        max-height: 50px;
                        margin-right: 10px;
                    }
                    .comics-item{
                        @include flex(row, center, center);
                        width: calc(100% / 5);
                    }
                }
            }
    }
    
</style>