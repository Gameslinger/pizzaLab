<template>
  <div class="home">
    <img alt="Pizza logo" src="../assets/img/logo.png" />
    <HelloWorld msg="Welcome to Tastee Pizza" />
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
<style>
.home{
background:#DAF5FF;
font-size:30pt;
color:#587291;
}
</style>
