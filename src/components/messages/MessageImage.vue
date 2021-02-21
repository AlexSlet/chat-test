<template>
    <div class="message messageImage">
        <img :src="message.messageBody" alt="message image">
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
    .messageImage img {
        max-width: 200px;
    }
</style>