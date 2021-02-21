<template>
    <div class="message__system">
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
    .message__system {
        align-self: center;
        color: #fff;
        background: #ccc;
        width: 100%;
        margin: 10px 0;
        font-size: 14px;
        padding: 2px;
    }
</style>