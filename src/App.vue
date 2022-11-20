<template>
  <div v-if="showModal">
    <BackModal
      :title="title"
      :content="content"
      :theme="theme"
      @close="showModal = false"
    />
  </div>
  <div v-if="showModalTwo">
    <BackModal
      title="Are u sure want to delete?"
      content="Yes or No"
      theme="delete"
      @close="showModalTwo = false"
    />
  </div>
  <button @click="showModal = true">Show Login Modal</button>
  <button @click="showModalTwo = true" class="orange">Show Delete Modal</button>
</template>

<script>
import BackModal from "./components/BackModal.vue";
export default {
  name: "App",
  data() {
    return {
      title: "Login Success",
      content: "Welcome user Lwin Ko Ko",
      theme: "success",
      showModal: false,
      showModalTwo: false,
    };
  },
  components: {
    BackModal,
  },
};
</script>

<style scoped>
button {
  padding: 15px 20px;
  border: none;
  background-color: royalblue;
  color: whitesmoke;
  margin: 20px;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}
.orange {
  background-color: orangered;
  margin-left: 5px;
}
</style>
