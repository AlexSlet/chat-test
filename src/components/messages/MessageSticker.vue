<template>
    <div class="message__sticker">
        {{message.messageBody}}
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
    .message__sticker {
        font-size: 40px;
    }
</style>