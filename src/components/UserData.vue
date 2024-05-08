<template>
  <form @submit.prevent="submitData">
    <div>
      <label>Name:</label>
      <input type="text" v-model="name">
    </div>
    <div>
      <label>Age:</label>
      <input type="number" v-model="age">
    </div>
    <button type="submit">Submit</button>
  </form>
</template>

<script>
  export default {
    emits: ['user-submitted'],
    data() {
      return {
        name: '',
        age: ''
      }
    },
    methods: {
      submitData() {
        this.$emit('user-submitted', {
          id: new Date().toISOString(),
          name: this.name,
          age: this.age
        });
        this.name = '';
        this.age = '';
      }
    }
  }
</script>