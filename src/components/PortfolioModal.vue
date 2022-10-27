<template>
    <transition name="fade">
        <div class="modal-wrap" v-show="visible" :class="{ active: visible }">
            <div class="dim" @click="modalClose"></div>
            <div class="modal-box">
                <div class="modal-header">{{ portfolioItem.name }}</div>
                <div class="modal-content">
                    <div class="info-box">
                        <dl>
                            <dt>기여도</dt>
                            <dd>{{ portfolioItem.percent }}%</dd>
                        </dl>
                        <dl>
                            <dt>유형</dt>
                            <dd>{{ portfolioItem.type }}</dd>
                        </dl>
                        <dl>
                            <dt>기간</dt>
                            <dd>{{ portfolioItem.term }}</dd>
                        </dl>
                        <dl>
                            <dt>기술</dt>
                            <dd>{{ portfolioItem.skill }}</dd>
                        </dl>
                    </div>
                    <p class="desc">{{ portfolioItem.desc }}</p>
                    <div class="btn-wrap">
                        <a
                            :href="portfolioItem.guide"
                            v-show="portfolioItem.guide"
                            target="_blank"
                            >Guide</a
                        >
                         <a
                            :href="portfolioItem.index"
                            v-show="portfolioItem.index"
                            target="_blank"
                            >Index</a
                        >
                        <a
                            :href="portfolioItem.site"
                            v-show="portfolioItem.site"
                            target="_blank"
                            >Site</a
                        >
                    </div>
                </div>
                <button class="btn-close" @click="modalClose">
                    <span class="hidden">닫기</span>
                </button>
            </div>
        </div>
    </transition>
</template>

<script>
export default {
    name: "PortfolioModal",
    props: {
        portfolioItem: Object,
        visible: Boolean,
    },
    data() {
        return {};
    },
    mounted() {},
    methods: {
        modalClose() {
            this.$emit("modalClose", false);
        },
    },
};
</script>

<style lang="scss" scoped></style>
