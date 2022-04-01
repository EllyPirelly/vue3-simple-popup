<template>
  <div class="modal-container" @click.self="closeModal">
    <div class="modal" :class="{ attention: theme === 'attention' }">
      <!-- default slot -->
      <slot></slot>
      <div class="link-container">
        <!-- named slot -->
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['theme'],

  methods: {
    closeModal() {
      this.$emit('closeevent')
    },
  },
}
</script>

<style lang="scss">
.modal-container {
  background-color: rgba(0, 0, 0, 0.5);
  height: 100%;
  position: fixed;
  top: 0;
  width: 100%;

  .modal {
    background-color: #fff;
    border-radius: 10px;
    margin: 100px auto;
    padding: 20px;
    width: 400px;
  }

  h1 {
    color: #808080;
    border: none;
    padding: 0;
  }

  p {
    font-style: normal;
  }

  .link-container {
    text-align: center;
    margin: 30px 0 10px 0;

    a {
      color: #333;
      padding: 8px;
      border: 2px solid #333;
      border-radius: 4px;
      text-decoration: none;
      margin: 10px;
    }
  }

  .attention {
    background-color: #dda0dd;

    h1 {
      color: #fff;
    }

    .link-container a {
      color: #800080;
      border: 1px solid #800080;
    }
  }
}
</style>
