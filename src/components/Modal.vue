<template>
  <div class="modal" @click="closeModal">
    <div class="backdrop" :class="{ attention: theme === 'attention' }">
      <h1>{{ header }}</h1>
      <p>{{ promo }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['header', 'promo', 'theme'],

  methods: {
    closeModal() {
      this.$emit('closeevent')
    },
  },
}
</script>

<style lang="scss">
.modal {
  background-color: rgba(0, 0, 0, 0.5);
  height: 100%;
  position: fixed;
  top: 0;
  width: 100%;
}

.modal .backdrop {
  background-color: #fff;
  border-radius: 10px;
  margin: 100px auto;
  padding: 20px;
  width: 400px;
}

.modal h1 {
  color: #808080;
  border: none;
  padding: 0;
}

.modal p {
  font-style: normal;
}

.modal .attention {
  background-color: #dda0dd;
}

.modal .attention h1 {
  color: #fff;
}
</style>
