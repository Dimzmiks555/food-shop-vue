<template >
    <div class="offer">
        <h2>50% скидка</h2>
        <p>на все бургеры </p>
    </div>
</template>
<script>
export default {
    name: 'Offer'
}
</script>
<style scoped>
    .offer {
        background: #ab97f3;
        padding: 30px;
        border-radius: 30px;
        color: #fff;
    }
    .offer h2 {
        margin: 10px 0;
        font-weight: 900;
        font-size: 32px;
    }
    .offer p {
        margin-bottom: 10px;
    }
</style>