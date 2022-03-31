<template>
  <h1>{{ title }}</h1>

  <div v-if="showModal">
    <Modal
      :header="header"
      :promo="promo"
      theme="attention"
      @closeevent="toggleModal"
    />
  </div>

  <button class="btn-primary" @click="toggleModal">Open Me</button>
</template>

<script>
import Modal from '../components/Modal.vue'

export default {
  name: 'About',

  components: {
    Modal,
  },

  data() {
    return {
      title: 'This is an about page with a modal',
      header: "I'm a modal you know what I mean",
      promo: 'and I do my little turn on the Vue walk',
      showModal: false,
    }
  },

  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
  },
}
</script>

<style lang="scss">
.btn-primary {
  margin-top: 20px;
  padding: 10px;

  &:hover {
    border: 2px solid #dda0dd;
  }
}
</style>
