<template>
  <div>
    <h3>My Profile</h3>
    <h4>{{ $route.params.id }}</h4>
    <router-link :to="{ name: 'Profile', query: { plan: 'private' } }"
      >Another Route</router-link
    >
    <h5>{{ $route.query }}</h5>
    <p><button v-on:click="goBack">go back</button></p>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Watch } from "vue-property-decorator";

@Component
export default class Profile extends Vue {
  mounted(): void {
    console.log(this.$route.params.id);
  }

  @Watch("$route", { immediate: true, deep: true })
  onRouteChange(to: unknown, from: unknown): void {
    console.log("to", to);
    console.log("from", from);
  }

  goBack = (): void => {
    window.history.length > 1 ? this.$router.go(-1) : this.$router.push("/");
  };
}
</script>
