<template>
    <div>ログアウト中…</div>
</template>

<script>
import firebase from "~/plugins/firebase";
export default {
  created() {
    firebase
      .auth()
      .signOut()
      .then(function() {
        console.log("sign out");
      });
  }
};
</script>