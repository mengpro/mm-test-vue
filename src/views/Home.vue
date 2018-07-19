<template>
  <div class="home">
    <img src="../assets/logo.png" :title="author">
    <HelloWorld v-if="isShowHello" msg="Welcome to Your Vue.js App" :title="tip"/>
    <EnvInput v-for="env in envs" :key="env.id" v-model="currentEnv" :env="env" v-on:input="currentEnv = $event"></EnvInput>
    <p>Current env: {{ currentEnv }}</p>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import EnvInput from '@/components/EnvInput.vue'

export default {
  name: 'home',
  data () {
    return {
      tip: "",
      isShowHello: true,
      envs: [
        { id: 1, title: "test" },
        { id: 2, title: "develop" },
        { id: 3, title: "production" }
      ],
      currentEnv: ''
    }
  },
  components: {
    HelloWorld, EnvInput
  },
  computed: {
    author: {
      get: function () {
        return this.tip.split(' ')[0]
      },
      set: function (newValue) {
        this.tip = newValue + " vue js"
      }
    },
    reversedTip: function () {
      return this.tip.split('').reverse().join('')
    }
  },
  created: function () {
    this.author = "mm"
    console.log("test success");
  }
}
</script>
