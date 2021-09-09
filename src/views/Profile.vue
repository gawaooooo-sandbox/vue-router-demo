<template>
  <div>
    <h3>My Profile</h3>
    <h4>{{ $route.params.id }}</h4>
    <p><button v-on:click="goBack">go back</button></p>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";

@Component
export default class Profile extends Vue {
  mounted(): void {
    console.log(this.$route.params.id);
  }
  goBack = (): void => {
    window.history.length > 1 ? this.$router.go(-1) : this.$router.push("/");
  };
}
</script>
