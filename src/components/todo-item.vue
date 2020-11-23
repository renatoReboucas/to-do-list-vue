<template>
  <div>
    <span> {{ item.text }} </span>
    <button @click="$emit('remove')">X</button>
  </div>
</template>

<script>
export default {
  props: {
    item: Object,
  },
};
</script>
