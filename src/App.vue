<script setup>
import { ref } from 'vue';
import { socket } from '@/socket';
import BaseLayout from './components/base-layout.vue';
import MessageField from './components/message-field.vue';

const messages = ref([]);

// Listen for event
socket.on('chat', function (data) {
  messages.value.push({
    handle: data.handle,
    message: data.message
  });
});
</script>

<template>
  <BaseLayout>
    <header>
      <h1 class="text-2xl text-white">Chat App</h1>
    </header>
    <section id="output" class="flex-1 overflow-y-auto py-4 my-4">
      <div v-for="(msg, index) in messages" :key="index" class="text-white mb-2">
        <strong>{{ msg.handle }}:</strong> {{ msg.message }}
      </div>
    </section>
    <MessageField />
  </BaseLayout>
</template>