<script>
export default {
    data() {
        return {
            menu:[
                {
                    title: "characters",
                    isActive: false,
                },
                {
                    title: "comics",
                    isActive: true,
                },
                {
                    title: "movies",
                    isActive: false,
                },
                {
                    title: "tv",
                    isActive: false,
                },
                {
                    title: "games",
                    isActive: false,
                },
                {
                    title: "collectibles",
                    isActive: false,
                },
                {
                    title: "videos",
                    isActive: false,
                },
                {
                    title: "fans",
                    isActive: false,
                },
                {
                    title: "news",
                    isActive: false,
                },
                {
                    title: "shop",
                    isActive: false,
                },
            ]
        }
    },
    methods: {
        imgPath: function(){
            return new URL(`../assets/img/dc-logo.png`, import.meta.url).href
        }
    },
}
</script>

<template>
    <div class="container">
        <header>
            <a href="#">
                <img :src="imgPath()" alt="logo-dc">
            </a>

            <nav>
                <a
                    href=""
                    v-for="item,index in menu"
                    :class="{active: item.isActive}"
                >
                    {{menu[index].title.toUpperCase()}}
                </a>
            </nav>
        </header>
    </div>

</template>

<style lang="scss" scoped>
    @use "../style/partials/mixin" as *;
    @use "../style/partials/variables" as *;

    .container{
        @include container(1280px, auto);
        header{
        @include flex(row, space-between, center);
        padding: 30px 0;
        nav {
            display: flex;
            gap: 1.6rem;
            a{
                color: $darkgrey-color;
                text-decoration: none;
                font-size: 0.9rem;
                font-weight: 600;

                &.active{
                    color: $blue-color;
                }
            }
        }
    }
    }
</style>