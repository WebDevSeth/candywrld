<template>
  <nav>
    <router-link class="but" to="/">HOME</router-link>
  </nav>

  <br />
  <br />

  <div class="Login">
    <form @submit.prevent="login" class="form neu-border">
      <h2 class="form-heading"></h2>
      <input
        class="form-input neu-border-inset"
        type="email"
        v-model="email"
        placeholder="Email"
        required
      />
      <input
        class="form-input neu-border-inset"
        type="password"
        v-model="password"
        placeholder="Password"
        required
      />
      <button type="submit" class="form-btn">Login</button>

      <!-- <div class="form-social-login">
      <button class="form-btn neu-border form-social-btn">
        <i class="fab fa-google"></i>
      </button>
      <button class="form-btn neu-border form-social-btn">
        <i class="fab fa-facebook-f"></i>
      </button>
    </div> -->

      <p>
        Not a member?
        <router-link to="/Register">Register</router-link>
      </p>
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    login() {
      fetch("https://pos-bkend.herokuapp.com/users/", {
        method: "PATCH",
        body: JSON.stringify({
          email: this.email,
          password: this.password,
        }),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
        },
      })
        .then((response) => response.json())
        .then((json) => {
          localStorage.setItem("jwt", json.jwt);
          alert("User logged in");
          this.$router.push({ name: "Products" });
        })
        .catch((err) => {
          alert(err);
        });
    },
  },
};
</script>
<style>
.neu-border {
  border-radius: 30px;
  background: #f5f5f5;
  box-shadow: 8px 8px 15px whitesmoke, -8px -8px 15px whitesmoke;
}
.neu-border-inset {
  border-radius: 30px;
  background: #f5f5f5;
  box-shadow: inset 8px 8px 15px whitesmoke, inset -8px -8px 15px whitesmoke;
}

.form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 40px;
  margin-top: 80px !important;
  gap: 20px;
  width: 100%;
  margin-inline: auto;
  max-width: 600px;
  font-size: 25px;
}

.form-heading {
  text-align: center;
  text-transform: uppercase;
}

.form-input,
.form-btn {
  border: none;
  outline: none;
  padding: 20px;
  font-size: 25px;
}

.form-btn {
  cursor: pointer;
  transition: all 0.1s linear;
}

.form-btn:hover {
  transform: scale(1.05);
}

.form-social-login {
  display: flex;
  justify-content: space-between;
}

.form-social-btn {
  width: 45%;
  color: #333;
}

.but {
  font-size: 35px !important;
  font-weight: bold;
  color: black;
}

.form-btn {
  background-color: #5ce1e6 !important;
}

.but:hover {
  color: yellow !important;
}
</style>
