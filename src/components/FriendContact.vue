<template>
  <li>
    <h2>{{ friend.name }} {{ name }}</h2>
    <button @click="toggleDetails">{{ detailsAreVisible ? 'Hide' : 'Show' }} Details</button>
    <ul v-if="detailsAreVisible">
      <li>Phone: {{ friend.phone }} {{ phoneNumber }}</li>
      <li>Email: {{ friend.email }}</li>
    </ul>
  </li>
</template>

<script>
export default {
  props: ['name', 'phoneNumber', 'emailAddress'],
  data() {
    return {
      detailsAreVisible: false,
      friend: {
        id: 'manuel',
        name: 'Manuel Lorenz',
        phone: '0 123455',
        email: 'manuel@mail.com',
      }
    }
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    }
  },
}
</script>