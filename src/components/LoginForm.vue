<template>
  <div>
    <div class="login-page">
      <div v-if="!registerActive" v-bind:class="{ error: inputNil }">
        <h1>Sign In</h1>
        <form>
          <input
            v-model="emailLogin"
            type="email"
            class="form-control"
            placeholder="Email"
            required
          />
          <input
            v-model="passwordLogin"
            type="password"
            class="form-control"
            placeholder="Password"
            required
          />
          <input type="submit" @click="letLogIn" />
          <p>
            Don't have an account?
            <a
              href="#"
              @click="(registerActive = !registerActive), (inputNil = false)"
              >Sign up here</a
            >
          </p>
          <p><a href="#">Forgot your password?</a></p>
        </form>
      </div>

      <div v-else class="card register" v-bind:class="{ error: inputNil }">
        <h1>Log in</h1>
        <form class="form-group">
          <input
            v-model="emailReg"
            type="email"
            class="form-control"
            placeholder="Email"
            required
          />
          <input
            v-model="passwordReg"
            type="password"
            class="form-control"
            placeholder="Password"
            required
          />
          <input
            v-model="confirmReg"
            type="password"
            class="form-control"
            placeholder="Confirm Password"
            required
          />
          <input type="submit" class="btn btn-primary" @click="letReg" />
          <p>
            Already have an account?
            <a
              href="#"
              @click="(registerActive = !registerActive), (inputNil = false)"
              >Sign in here</a
            >
          </p>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      registerActive: false,
      emailLogin: "",
      passwordLogin: "",
      emailReg: "",
      passwordReg: "",
      confirmReg: "",
      inputNil: false,
    };
  },

  methods: {
    letLogIn() {
      if (this.emailLogin === "" || this.passwordLogin === "") {
        this.inputNil = true;
      } else {
        alert("You are now logged in");
      }
    },

    letReg() {
      if (
        this.emailReg === "" ||
        this.passwordReg === "" ||
        this.confirmReg === ""
      ) {
        this.inputNil = true;
      } else {
        alert("You are now registered");
      }
    },
  },
};
</script>
<style  scoped>
.login-page {
  width: 250px;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  justify-content: space-between;
  margin: 30px 0px 20px 20px;
  padding: 50px 10px;

  background-color: #fff;
  padding: 15px;
  box-shadow: 0px 2px 2px 3px rgba(84, 84, 84, 0.36);
  border-radius: 2px;
}
form input {
  margin: 10px 0px;
}
</style>