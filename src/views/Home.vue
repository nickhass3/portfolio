<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/profile-photo.png" />
    <HelloWorld msg="Hi, I'm Nick" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
};
</script>
