<template>
  <h1>{{ title }}</h1>
  <p>{{ context }}</p>

  <!-- modal one -->
  <div v-if="showModal">
    <!-- slot default - content passed down to modal -->
    <Modal theme="attention" @closeevent="toggleModal">
      <h1>Modal One Headline</h1>
      <p>Modal One p tag</p>

      <!-- slot named - content passed down to modal -->
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
    </Modal>
  </div>

  <!-- modal two -->
  <div v-if="showModalTwo">
    <Modal theme="attention" @closeevent="toggleModalTwo">
      <h1>Modal Two Headline</h1>
      <p>Modal Two p tag</p>

      <template v-slot:links>
        <a href="#">click for fun</a>
      </template>
    </Modal>
  </div>

  <div class="btn-primary-wrapper">
    <button class="btn-primary" @click="toggleModal">Open Modal One</button>
    <button class="btn-primary" @click="toggleModalTwo">Open Modal Two</button>
  </div>
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
      context: 'Content in Modals in coming in via Vue slots',
      showModal: false,
      showModalTwo: false,
    }
  },

  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },

    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    },
  },
}
</script>

<style lang="scss">
.btn-primary {
  margin-top: 20px;
  padding: 10px;

  &:not(:last-child) {
    margin-right: 20px;
  }

  &:hover {
    border: 2px solid #dda0dd;
  }
}

.btn-primary-wrapper {
  display: flex;
  justify-content: center;
}
</style>
