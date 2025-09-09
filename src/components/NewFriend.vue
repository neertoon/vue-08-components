<template>
  <form>
    <div>
      <label>Name</label>
      <input type="text" name="name">
    </div>

    <div>
      <label>Phone</label>
      <input type="text" name="phoneNumber">
    </div>

    <div>
      <label>Email</label>
      <input type="email" name="emailAddress">
    </div>

    <div>
      <button>Add contact</button>
    </div>
  </form>
</template>

<script>
export default {
  emits: ['save'],
  data() {
    return {
      detailsAreVisible: false,
    }
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      this.$emit('toggle-favorite', this.id);
    }
  },
}
</script>