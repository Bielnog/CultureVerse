<template>
  <v-app>
    <SideBar>
      <v-main>
        <Home msg="Welcome to the homepage!" />
      </v-main>
    </SideBar>
  </v-app>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Home from "./components/Home.vue";
import SideBar from "./components/SideBar.vue";

export default defineComponent({
  name: "App",
  components: {
    Home,
    SideBar,
  },
});
</script>

<style>
.v-main {
  padding: 16px;
}
</style>
