<template>
  <div>
    <h2>{{name}}</h2>
    <p>{{body}}</p>
  </div>
</template>

<script>
import profiles from "./memberProfiles";
export default {
  computed: {
    id() {
      return +this.$route.params.id;
    },
    myProfile() {
      const profile = profiles.find(profile => profile.id === this.id);
      if (!profile) {
        return {
          name: "メンバーがいません",
          profile: ""
        };
      }
      return profile;
    },
    name() {
      return this.myProfile.name;
    },
    body() {
      return this.myProfile.profile;
    }
  }
};
</script>

<style>
</style>
