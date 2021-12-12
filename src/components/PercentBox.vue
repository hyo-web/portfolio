<template>
    <svg viewBox="0 0 36 36" class="circular-chart">
        <path
            class="circle"
            :stroke-dasharray="percent + ', 100'"
            d="M18 2.0845
			a 15.9155 15.9155 0 0 1 0 31.831
			a 15.9155 15.9155 0 0 1 0 -31.831"
        />
    </svg>
</template>

<script>
export default {
    name: "PercentBox",
    props: {
        percent: Number,
    },
    data() {
        return {};
    },

    mounted() {},

    methods: {},
};
</script>

<style lang="scss" scoped></style>
