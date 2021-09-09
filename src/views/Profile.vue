<template>
  <div>
    <h3>My Profile</h3>
    <p><button v-on:click="goBack">go back</button></p>
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-property-decorator";
export default class Profile extends Vue {
  goBack = (): void => {
    window.history.length > 1 ? this.$router.go(-1) : this.$router.push("/");
  };
}
</script>
