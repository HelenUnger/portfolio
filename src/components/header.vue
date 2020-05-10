<template>
    <div ref="header" class="header-bg">
        <div class="bubble"></div>
        <div class="bubble"></div>
        <div class="bubble"></div>
        <div class="bubble"></div>
        <div class="bubble"></div>
        <div class="bubble"></div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            message: 'message',
        };
    },

    mounted() {
        this.$refs.header.addEventListener("mousemove", this.mouseMove);
    },

    methods: {
        mouseMove(event) {
            console.log(event);
        }
    }
}
</script>
<style lang="scss">
    .header-bg {
        height: 100vh;
    }

    .bubble {
        border-radius: 50%;
        &:nth-of-type(1) {
            position: absolute;
            top: -20px;
            width: 40vw;
            height: 40vw;
            background: rgb(192,29,253);
            background: linear-gradient(45deg, rgba(192,29,253,1) 21%, rgba(207,66,206,1) 94%);
        }
        &:nth-of-type(2) {
            width: 100px;
            height: 100px;
            background-color: red;
        }
        &:nth-of-type(3) {
            width: 100px;
            height: 100px;
            background-color: green;
        }
        &:nth-of-type(4) {
            width: 100px;
            height: 100px;
            background-color: yellow;
        }
        &:nth-of-type(5) {
            width: 100px;
            height: 100px;
            background-color: pink;
        }
        &:nth-of-type(6) {
            width: 100px;
            height: 100px;
            background-color: purple;
        }
    }
</style>