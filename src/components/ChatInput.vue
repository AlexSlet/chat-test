<template>
  <div class="chat__input">
    <input type="text" v-model="messageText" />
    <input type="button" value="Send" @click="sendMessage()" />
  </div>
</template>
<script>
export default {
  name: "ChatInput",
  data() {
    return {
      messageText: "",
    };
  },
  methods: {
    sendMessage() {
      if (this.messageText.trim() !== "") {
        this.$emit("send-message", this.messageText);
        this.messageText = '';
      }
    },
  },
};
</script>
<style scoped>
.chat__input {
  position: absolute;
  width: 100%;
  bottom: 0;
  left: 0;
  display: flex;
  border-top: 1px solid #42b983;
}

.chat__input input[type="text"] {
  width: 90%;
  padding: 10px;
  outline: none;
  border: none;
}

.chat__input input[type="button"] {
    width: 10%;
  background: #42b983;
  color: #fff;
  font-weight: 700;
  border: none;
  outline: none;
  cursor: pointer;
  transition: all 0.3s ease;
  border-left: 1px solid #42b983;
  text-transform: uppercase;
  padding: 0 10px;
}

.chat__input input[type="button"]:hover {
  background: #fff;
  color: #42b983;
}
</style>