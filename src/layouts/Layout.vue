<template>
    <div class="layout">
        <Header></Header>
        <main class="page">
            <slot ></slot>
        </main>
    </div>
</template>

<script>

import Header from './Header.vue';

export default {
    name: "Layout",
    components: { Header }
}
</script>

<style scoped>


    .layout {
        margin: 40px 5%;
        min-height: calc(100vh - 80px);
        border-radius: 25px;
        background: #e9f3fe;
        box-shadow: inset 0 0 40px #fff;
        display: flex;
    }

    .page {
        margin-left: 40px;
        margin: 40px 40px 40px 0;
        border-radius: 20px;
        padding: 30px 60px;
        width: 80%;
        background: #fff;
    }

</style>