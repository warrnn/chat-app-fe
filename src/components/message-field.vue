<template>
  <div class="grid grid-cols-12 gap-3 items-center">
    <input type="text"
      class="col-span-10 sm:col-span-11 w-full bg-stone-700/50 text-white border border-stone-600 rounded-xl py-3 px-4 focus:outline-none focus:border-blue-500 focus:ring-1 focus:ring-blue-500 transition-all placeholder:text-stone-400"
      placeholder="Type a message...">
    <button
      class="col-span-2 sm:col-span-1 w-full flex items-center justify-center bg-blue-600 hover:bg-blue-500 text-stone-900 font-bold rounded-xl py-3 px-4 transition-all duration-200 active:scale-95 shadow-md shadow-blue-900/20">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-5 h-5">
        <path
          d="M3.478 2.404a.75.75 0 0 0-.926.941l2.432 7.905H13.5a.75.75 0 0 1 0 1.5H4.984l-2.432 7.905a.75.75 0 0 0 .926.94 60.519 60.519 0 0 0 18.445-8.986.75.75 0 0 0 0-1.218A60.517 60.517 0 0 0 3.478 2.404Z" />
      </svg>
    </button>
  </div>
</template>