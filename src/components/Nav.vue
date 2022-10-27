<template>
    <nav class="nav-wrap">
        <ul>
            <li><a href="#" v-scroll-to="'#about'">About</a></li>
            <li class="active"><a href="#" v-scroll-to="'#portfolio'">Portfolio</a></li>
           <!--  <li>
                <a href="#" v-scroll-to="'#visual'"><strong>TOP</strong></a>
            </li> -->
        </ul>
    </nav>
</template>

<script>
export default {
    name: "Nav",

    data() {
        return {};
    },

    mounted() {},

    methods: {},
};
</script>

<style lang="scss" scoped></style>
