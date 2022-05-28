<template>

  <div>
    <h2>Witaj {{ email }}</h2>
    <button @click="getout()">{{ buttonLabel }}</button>

  </div>
</template>

<script>
export default {
  props: ['email','buttonLabel'],

  data() {
    return {
      email: ''
    }
  },
  methods: {
    getout() {a
      this.$emit('logout');
    }
  }
}
</script>