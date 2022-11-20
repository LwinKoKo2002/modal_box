<template>
  <div class="backdrop" @click.self="hideModal">
    <div
      class="modal"
      :class="{ success: theme === 'success', danger: theme === 'delete' }"
    >
      <h2>{{ title }}</h2>
      <p>{{ content }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "content", "theme"],
  methods: {
    hideModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.backdrop {
  top: 0;
  position: fixed;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}
.modal {
  width: 500px;
  background-color: white;
  margin: 100px auto;
  border-radius: 10px;
  padding: 25px;
}
h2 {
  margin-bottom: 10px;
}
.success {
  background-color: green;
  color: whitesmoke;
}
.danger {
  background-color: crimson;
  color: white;
}
</style>