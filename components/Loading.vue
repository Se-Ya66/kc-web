<template>
    <div v-if="loading" class="loading-page">
        <transition name="logo">
            <img src="../static/logo.png" class="logo">
        </transition>
    </div>
</template>

<script>
export default {
    data: () => ({
        loading: false
    }),
    methods: {
        start() {
        this.loading = true
        },
        finish() {
        this.loading = false
        }
    }
}
</script>

<style scoped>
.loading-page {
    background-color: rgba(0, 0, 0, 0.8);
    width:100%;
    height:100vh;
    position: fixed;
    left: 0;
    top: 0;
}
.logo{
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
    width:20%;
    z-index:2;
}
.logo-leave-active,
.logo-enter-active {
    transform: scale(0, 0);
    transition: transform 0.7s;
}
.logo-enter-to, .logo-leave {
    transform: scale(1, 1);
}
</style>