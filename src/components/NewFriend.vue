<template>
  <form @submit.prevent="submitData">
    <div>
      <label>Name</label>
      <input type="text" name="name" v-model="enteredName">
    </div>

    <div>
      <label>Phone</label>
      <input type="text" name="phoneNumber" v-model="enteredPhone">
    </div>

    <div>
      <label>Email</label>
      <input type="email" name="emailAddress" v-model="enteredEmail">
    </div>

    <div>
      <button>Add contact</button>
    </div>
  </form>
</template>

<script>
export default {
  emits: ['add-contact'],
  data() {
    return {
      enteredName: '',
      enteredPhone: '',
      enteredEmail: '',
    }
  },
  methods: {
    submitData() {
      this.$emit('add-contact', { name: this.enteredName, phone: this.enteredPhone, email: this.enteredEmail });
    }
  },
}
</script>