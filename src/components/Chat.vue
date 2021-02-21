<template>
  <div class="chat">
    <div class="chat__container">

      <template v-for="message in messages" :key="message.messageID">
        <component v-bind:is="currentComponent(message)" :message="message"></component>
      </template>

      <chat-input @send-message="sendMessage($event)"></chat-input>
    </div>
  </div>
</template>

<script>
import chatInput from './ChatInput';
import messageText from './messages/MessageText';
import messageImage from './messages/MessageImage';
import messageGallery from './messages/MessageGallery';
import messageSystem from './messages/MessageSystem';
import messageSticker from './messages/MessageSticker';

export default {
  name: "Chat",
  components: {
    chatInput,
    messageText,
    messageImage,
    messageGallery,
    messageSystem,
    messageSticker
  },
  data() {
    return {
      messages: [
        {
          messageID: 0,
          messageBody: 'Hello world!',
          messageType: 'text'
        },
        {
          messageID: 1,
          messageBody: 'https://cdn.auth0.com/blog/logos/vuejs-logo.png',
          messageType: 'image',
        },
        {
          messageID: 2,
          messageBody: [
            'https://i.imgur.com/U6thwX0.jpg',
            'https://i.imgur.com/U6thwX0.jpg',
            'https://i.imgur.com/U6thwX0.jpg'
          ],
          messageType: 'gallery',
        },
        {
          messageID: 3,
          messageBody: 'Unread messages ▼',
          messageType: 'system',
        },
        {
          messageID: 4,
          messageBody: '😁',
          messageType: 'sticker',
        },
      ]
    }
  },
  methods: {
    currentComponent(message) {
      switch(message.messageType) {
        case 'text': return 'messageText';
        case 'image': return 'messageImage';
        case 'gallery': return 'messageGallery';
        case 'system': return 'messageSystem';
        case 'sticker': return 'messageSticker';
      }
    },
    sendMessage(messageText) {
      this.messages.push({
        messageID: Date.now(),
        messageBody: messageText,
        messageType: 'text'
      })
    }
  }
};
</script>

<style scoped>
.chat {
  display: flex;
  justify-content: center;
  align-items: center;
  overflow-y: auto;
}

.chat__container {
  min-width: 600px;
  margin: 0 auto;
  border: 1px solid #42b983;
  border-radius: 4px;
  position: relative;
  overflow: hidden;
  padding: 40px 0;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: flex-end;
  overflow-y: auto;
  overflow-x: hidden;
}

.chat__container:before {
  content: 'Vue.js Chat';
  position: absolute;
  width: 100%;
  padding: 10px;
  background: #42b983;
  color: #fff;
  text-align: center;
  left: 0;
  top: 0;
  font-weight: 700;
}
</style>
