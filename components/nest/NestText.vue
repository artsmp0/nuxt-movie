<script setup lang="ts">
const props = defineProps<{
  text: string;
}>();
</script>

<template>
  <div style="color: red">{{ props.text }}</div>
</template>

<style lang="less" scoped></style>
