<template>
  <Chat />
</template>

<script>
import Chat from "./components/Chat.vue";

export default {
  name: "App",
  components: {
    Chat,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.message {
  padding: 10px;
  border: 1px solid #42b983;
  border-radius: 10px 10px 0 10px;
  margin: 2px;
  margin-right: 5px;
  font-weight: 700;
  max-width: 60%;
  text-align: left;
}
</style>
