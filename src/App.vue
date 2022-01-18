<script>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import MyButton from './components/MyButton.vue'
import MyInput from './components/MyInput.vue'

export default {
  components: {
    MyButton,
    MyInput,
  },

  data() {
    return {
      valid: true,
      username: {
        value: 'user',
        error: ''
      },
      password: {
        value: 'Thisisit2022',
        error: ''
      },
    }
  },

  computed: {
    valid(){
      return (
        !this.username.error &&
        !this.password.error
      )
    }
  },

  methods: {
    update({name, value, error}) {
      this[name].value = value
      this[name].error = error
    }

    submit($event){
      $event.preventDefault()
    }
  }
}
</script>

<template>
  <form v-on:submit="submit">
    <MyInput name="username" v-bind:rules="{required: true, min:5}" 
      v-bind:value="username.value"
      v-bind:error="username.error"
      v-on:update="update"
    />
    <MyInput name="password" v-bind:rules="{required: true, min:10}" 
      v-bind:value="password.value"
      type="password"
      v-bind:error="password.error"
      v-on:update="update"
    />
    <MyButton background="red" color="yellow" v-bind:disabled="!valid" />
  </form>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
