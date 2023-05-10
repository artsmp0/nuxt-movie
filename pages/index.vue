<script setup lang="ts">
// const NestText = resolveComponent('NestText');

const show = ref(false);
</script>

<template>
  <div>
    <NestButton />
    <!-- <component :is="NestText" :text="'hello world'" /> -->
    <LazyNestText v-if="show" text="hello lazy nuxt component" />
    <button @click="show = true">add lazy comp</button>
  </div>
</template>
