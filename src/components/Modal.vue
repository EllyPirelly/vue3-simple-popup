<template>
  <div class="modal-container" @click.self="closeModal">
    <div
      class="modal"
      :class="{ attention: theme === 'attention', promo: theme === 'promo' }"
    >
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

  p {
    font-style: normal;
  }

  .link-container {
    margin: 30px 0 10px 0;
    text-align: center;

    a {
      color: #333;
      border: 2px solid #333;
      border-radius: 4px;
      margin: 10px;
      padding: 8px;
      text-decoration: none;
    }
  }

  .attention {
    background-color: #dda0dd;

    h1,
    p,
    a {
      color: #800080;
    }

    p {
      font-weight: bold;
      margin-top: 10px;
    }

    .link-container a {
      border: 1px solid #800080;
      color: #fff;
      font-weight: bold;

      &:hover {
        background-color: #800080;
      }
    }
  }

  .promo {
    background-color: #6c6cdc;

    h1,
    p,
    a {
      color: #fff;
    }

    p {
      margin-top: 10px;
      font-weight: bold;
    }

    .link-container a {
      border: 1px solid #fff;
      font-weight: bold;

      &:hover {
        background-color: #fff;
        color: #6c6cdc;
      }
    }
  }
}
</style>
