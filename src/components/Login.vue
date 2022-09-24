<template>
  <div>
    <div class="login-page">
      <div class="login-card">
        <div class="text-center">
          <img src="img/lock.png" class="login-card__icon" alt="" />
          <h2>User Login</h2>
        </div>

        <form action="">
          <span>Email</span>
          <input type="email" placeholder="Enter Your Email" />

          <span>Password</span>
          <input type="password" placeholder="Enter Your Password" />
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
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
.mmmm {
  margin-top: 10px;
}
</style>
