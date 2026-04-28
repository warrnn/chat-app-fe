<script setup>
import BaseLayout from './components/base-layout.vue';
import MessageField from './components/message-field.vue';
</script>

<template>
  <BaseLayout>
    <header>
      <h1 class="text-2xl text-white">Chat App</h1>
    </header>
    <section class="flex-1 overflow-y-auto py-4">

    </section>
    <MessageField />
  </BaseLayout>
</template>