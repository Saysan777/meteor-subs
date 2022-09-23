<template>
  <form class="login-form" @submit.prevent="handleSubmit">
    <div class="forms">
      <label for="username">Username</label>
      <input
        id="username"
        name="username"
        type="text"
        placeholder="Enter Username"
        required
        v-model="username"
      />
    </div>

    <div>
      <label for="password">Password</label>
      <input
        id="password"
        name="password"
        type="password"
        placeholder="Enter Password"
        required
        v-model="password"
      />
    </div>
    <div class="img">
      <img v-bind:src="images" />
    </div>

    <div>
      <button type="submit">Log In</button>
    </div>
  </form>
</template>

<script>
import { Meteor } from "meteor/meteor";

export default {
  name: "LoginForm",
  data() {
    return {
      username: "",
      password: "",
      images: require("../../images/todo-pic.jpg"),
    };
  },
  methods: {
    handleSubmit(event) {
      Meteor.loginWithPassword(this.username, this.password);
    },
  },
};
</script>
<style scoped>
form {
  margin: 70px 10px 10px 450px;
  border: 4px solid gray;
  height: 500px;
  width: 800px;
  border-radius: 28px;
  box-shadow: 5px 8px 5px 7px;
}
.images {
  /* position: absolute;k */
}
input {
  border-radius: 12px;
}
button {
  padding: 12px;
  border-radius: 12px;
}
</style>
