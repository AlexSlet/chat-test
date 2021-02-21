<template>
    <div class="message messageGallery">
        <img :src="img" alt="image" v-for="img in message.messageBody" :key="img">
    </div>
</template>
<script>
export default {
    props: {
        message: {
            type: Object
        }
    }
}
</script>
<style scoped>
    .messageGallery {
        display: grid;
        grid-template-columns: 1fr 1fr;
        max-width: 60%;
    }

    img {
        max-width: 150px;
        margin: 2px;
    }
</style>