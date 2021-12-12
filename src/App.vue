<template>
    <div id="app">
        <Nav/>
        <transition name="view" mode="out-in">
            <router-view class="view-area" />
        </transition>
    </div>
</template>

<script>
import Nav from "@/components/Nav";

export default {
    components: {
        Nav,
    },
    data() {
        return {};
    },
    mounted() {},
    methods: {},
};
</script>
<style lang="scss">
@import "./assets/css/common";
</style>
