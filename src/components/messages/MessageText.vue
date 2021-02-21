<template>
    <div class="message message__text">
        {{ message.messageBody }}
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
<style>
</style>