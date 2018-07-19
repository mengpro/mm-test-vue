<template>
  <div class="env-input">
    <input type="radio" :id="'env' + env.id" :value="env.title" v-on:input="$emit('input', $event.target.value)">
    <label :for="'env' + env.id">{{ env.title }}</label>
  </div>
</template>

<script>
export default {
  name: 'EnvInput',
  props: {
    env: Object,
  }
}
</script>
