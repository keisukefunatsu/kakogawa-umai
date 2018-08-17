<template>
  <section class="container">
    <div>
    </div>
  </section>
</template>

<script>
import firebase from "~/plugins/firebase";
export default {
  components: {},
  created() {
    firebase.auth().onAuthStateChanged(function(user) {
      if (user) {
        alert("user logged in" + user.email);
        console.log(user);
      } else {
        alert("no user");
      }
    });
  }
};
</script>

<style>
</style>

