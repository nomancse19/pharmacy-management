<template>
  <login></login>
  <div class="toasts">
    <the-toast
      v-for="(toast, i) in toasts"
      :key="i"
      :toastType="toast.Type"
      :message="toast.message"
    ></the-toast>
  </div>
</template>

<script>
import Login from "./components/Login.vue";
import TheToast from "./components/TheToast.vue";
export default {
  components: {
    Login,
    TheToast,
  },
  data: () => ({
    toasts: [
      // {
      //   Type: "Success",
      //   message: "This Is Success Message",
      // },
      // {
      //   Type: "Error",
      //   message: "This Is Error Message",
      // },
    ],
  }),
  mounted() {
    this.$eventBus.on("toast", (data) => {
      this.toasts.push(data);
      this.removeOneToast();
    });
  },
  methods: {
    removeOneToast() {
      setTimeout(() => {
        this.toasts.shift();
      }, 2222);
    },
  },
};
</script>

<style></style>
