<script setup>
import { socket } from '@/socket';
import { ref } from 'vue';

const handle = ref('');
const message = ref('');

// Emit events
const sendMessage = () => {
  socket.emit('chat', {
    message: message.value,
    handle: handle.value
  });

  message.value = '';
};

const updateFeedback = () => {
  socket.emit('typing', handle.value);
}
</script>

<template>
  <div class="flex gap-3 items-center">
    <input type="text" id="Handle" v-model="handle"
      class="w-1/4 sm:w-1/5 bg-stone-700/50 text-white border border-stone-600 rounded-xl py-3 px-4 focus:outline-none focus:border-blue-500 focus:ring-1 focus:ring-blue-500 transition-all placeholder:text-stone-400"
      placeholder="Handle?">
    <input type="text" id="message" v-model="message" @keyup.enter="sendMessage" @keypress="updateFeedback"
      class="flex-1 bg-stone-700/50 text-white border border-stone-600 rounded-xl py-3 px-4 focus:outline-none focus:border-blue-500 focus:ring-1 focus:ring-blue-500 transition-all placeholder:text-stone-400"
      placeholder="Type a message...">
    <button id="send" @click="sendMessage"
      class="shrink-0 flex items-center justify-center bg-blue-600 hover:bg-blue-500 text-stone-900 font-bold rounded-xl py-3 px-4 transition-all duration-200 active:scale-95 shadow-md shadow-blue-900/20">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-5 h-5">
        <path
          d="M3.478 2.404a.75.75 0 0 0-.926.941l2.432 7.905H13.5a.75.75 0 0 1 0 1.5H4.984l-2.432 7.905a.75.75 0 0 0 .926.94 60.519 60.519 0 0 0 18.445-8.986.75.75 0 0 0 0-1.218A60.517 60.517 0 0 0 3.478 2.404Z" />
      </svg>
    </button>
  </div>
</template>