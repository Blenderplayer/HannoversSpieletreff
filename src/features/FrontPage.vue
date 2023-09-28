<template>
    <BasicLayout ref="Layout" class="h-100 bg-secondary mainBackground overflow-hidden">
        <template #background>
            <div class="position-relative w-100 h-100 opacity-25">
                <Card
                    v-for="index in 50"
                    :key="'card'+index"
                />
            </div>
        </template>
        <template #leftside>
            <div v-if="!smallSize" class="d-flex flex-column h-100 justify-content-center">
                <AtomicButton
                    class="neonGlowOutline m-4"
                    title="Informationen"
                    style="font-size: 1.5rem;"
                    @click="site = 0"
                />
                <AtomicButton
                    class="neonGlowOutline m-4"
                    title="Events"
                    style="font-size: 1.5rem;"
                    @click="site = 1"
                />
            </div>
        </template>
        <template #main>
            <div class="d-flex flex-column h-100">
                <div v-if="smallSize" class="">
                    <AtomicButton
                        class="neonGlowOutline m-4"
                        title="Informationen"
                        style="font-size: 1.5rem;"
                        @click="site = 0"
                    />
                    <AtomicButton
                        class="neonGlowOutline m-4"
                        title="Events"
                        style="font-size: 1.5rem;"
                        @click="site = 1"
                    />
                </div>
                <div class="contentFrame">
                    <Information v-if="site === 0"/>
                    <F_Events v-if="site === 1"/>
                </div>
            </div>
        </template>
        <template #rightside>

        </template>
    </BasicLayout>
</template>

<script>
/* eslint-disable vue/no-unused-components */
import BasicLayout from "@/layout/BasicLayout";
import AtomicButton from "@/atomics/AtomicButton";
import Information from "@/features/f_Information";
import Card from "@/atomics/Card";
import F_Events from "@/features/f_Events";

export default {
    name: "FrontPage",
    components: {F_Events, Card, Information, AtomicButton, BasicLayout},
    emits: [],
    props: {},
    mounted() {
        this.isSmallSize();
        window.addEventListener("resize", this.isSmallSize);
    },
    unmounted() {
        window.removeEventListener("resize", this.isSmallSize);
    },
    data() {
        return {
            site: 0,
            smallSize: false,
            loading: false,
        }
    },
    computed: {},
    methods: {
        isSmallSize() {
            this.smallSize = this.$refs.Layout.$el.clientWidth < 1000
        }
    },
}
</script>

<style scoped>
.contentFrame {
    background-color: #b7b7b788;
    height: 100%;
    overflow: auto;
    padding: 10px;
}
</style>