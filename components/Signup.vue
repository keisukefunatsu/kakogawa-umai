<template>
        <div class="column">  
        <h2>サインアップ</h2>
        <form class="form-horizontal" >
        <fieldset>

        <!-- Form Name -->
        <legend>Form Name</legend>

        <!-- Text input-->
        <div class="field">
        <label class="label" for="textinput-0">Text Input</label>
        <div class="control">
            <input v-model="username" id="textinput-0" name="textinput-0" type="text" placeholder="placeholder" class="input ">
        </div>
        </div>

        <!-- Password input-->
        <div class="field">
        <label class="label" for="passwordinput-0">Password Input</label>
        <div class="control">
            <input v-model="password" id="passwordinput-0" name="passwordinput-0" type="password" placeholder="placeholder" class="input ">
        </div>
        </div>

        </fieldset>
        <button @click.prevent.once="signUp">登録</button>
        </form>
        {{username}}
        {{password}}
    </div>
</template>

<script>
import firebase from "~/plugins/firebase";
export default {
  data() {
    return {
      username: "",
      password: ""
    };
  },
  methods: {
    signUp(username, password) {
      firebase
        .auth()
        .createUserWithEmailAndPassword(this.username, this.password)
        .then(user => {
          alert("user created :" + user.email);
        })
        .catch(error => {
          alert(error.message);
        });
    }
  }
};
</script>