<template>
  <div>
    <div class="login-page">
      <div class="login-card">
        <div class="text-center">
          <img src="img/lock.png" class="login-card__icon" alt="" />
          <h2>User Login</h2>
        </div>

        <form action="#" @submit.prevent="handleSubmit">
          <label>Email</label><br />
          <input
            type="email"
            v-model="formData.email"
            placeholder="Enter Your Email"
          />

          <label class="d-block mt-3">Password</label>
          <input
            type="password"
            v-model="formData.password"
            placeholder="Enter Your Password"
            ref="password"
          />
          <button type="submit" class="w-100 mt-3">Login</button>
          <div class="d-flex mt-3 jc-between">
            <div>
              <label for=""
                ><input type="checkbox" name="" id="" />
                Remember Me
              </label>
            </div>
            <div>
              <a href="">Forget Password</a>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    formData: {
      email: "",
      password: "",
    },
  }),
  methods: {
    handleSubmit() {
      if (!this.formData.email) {
        //alert("Email Can't be Empty");
        this.$eventBus.emit("toast", {
          Type: "Error",
          message: "Email Can Not Be Empty",
        });
        return;
      }
      if (this.formData.password.length <= 6) {
        // alert(
        //"Password Must Be 6 Character Long" + this.formData.password.length
        // );
        this.$eventBus.emit("toast", {
          Type: "Error",
          message: "Password Must Be 6 Character Long",
        });
        this.$refs.password.focus();
        return;
      } else {
        this.$eventBus.emit("toast", {
          Type: "Success",
          message: "Your Login Validation Success",
        });
      }
    },
  },
};
</script>

<style>
.login-page {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgb(235, 235, 235);
}
.login-card {
  width: 400px;
  min-height: 193px;
  background-color: #fff;
  border-radius: 5px;
  padding: 44px 33px;
  box-shadow: 0px 2px 9px 4px #dfdfdf;
}
.login-card input[type="email"],
.login-card input[type="password"] {
  width: 100%;
}
.login-card__icon {
  max-width: 77px;
}
input {
  padding: 7px 5px;
}
button {
  padding: 7px 5px;
  background-color: #290c0b;
  color: #fff;
  cursor: pointer;
}
</style>
