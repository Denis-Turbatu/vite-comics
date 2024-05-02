<script>
export default {
    data() {
        return {
            menu:[
                {
                    title: "CHARACTERS",
                    isActive: false,
                },
                {
                    title: "COMICS",
                    isActive: true,
                },
                {
                    title: "MOVIES",
                    isActive: false,
                },
                {
                    title: "TV",
                    isActive: false,
                },
                {
                    title: "GAMES",
                    isActive: false,
                },
                {
                    title: "COLLECTIBLES",
                    isActive: false,
                },
                {
                    title: "VIDEOS",
                    isActive: false,
                },
                {
                    title: "FANS",
                    isActive: false,
                },
                {
                    title: "NEWS",
                    isActive: false,
                },
                {
                    title: "SHOP",
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
                    {{menu[index].title}}
                </a>
            </nav>
        </header>
    </div>

</template>

<style lang="scss" scoped>
    @use "../style/partials/mixin" as *;

    .container{
        @include container(1180px, auto);
        header{
        @include flex(row, space-between, center);
        padding: 15px 0;
        nav {
            display: flex;
            gap: 1.6rem;
            a{
                color: #1c1c1c;
                text-decoration: none;
            }
        }
    }
    }
</style>