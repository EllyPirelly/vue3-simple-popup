<template>
  <div class="about">
    <h1>{{ title }}</h1>
    <p>{{ context }}</p>

    <!-- modal one -->
    <div v-if="showModal">
      <!-- slot default - content passed down to modal -->
      <Modal theme="attention" @closeevent="toggleModal">
        <h1>Modal one headline</h1>
        <p>Modal one p tag</p>

        <!-- slot named - content passed down to modal -->
        <template v-slot:links>
          <a href="#">sign up now</a>
          <a href="#">more info</a>
        </template>
      </Modal>
    </div>

    <!-- modal two -->
    <div v-if="showModalTwo">
      <Modal theme="promo" @closeevent="toggleModalTwo">
        <h1>Modal two headline</h1>
        <p>Modal two p tag</p>

        <template v-slot:links>
          <a href="#">click for fun</a>
        </template>
      </Modal>
    </div>

    <div class="btn-primary-wrapper">
      <button class="btn-primary" @click="toggleModal">open modal one</button>
      <button class="btn-primary" @click="toggleModalTwo">
        open modal two
      </button>
    </div>
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
      title: 'This is an about page with two modals',
      context: 'Content in modals in coming in via Vue slots',
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
.about {
  margin-top: 30px;
}

.btn-primary {
  background-color: rgba(44, 62, 80, 0.2);
  border: 1px solid #2c3e50;
  border-radius: 6px;
  margin-top: 20px;
  padding: 10px;

  &:not(:last-child) {
    margin-right: 20px;
  }

  &:hover {
    background-color: rgba(44, 62, 80, 0.5);
    color: #fff;
  }
}

.btn-primary-wrapper {
  display: flex;
  justify-content: center;
}
</style>
