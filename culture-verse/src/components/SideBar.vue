<template>
  <v-app>
    <!-- App Bar -->
    <v-app-bar app color="grey-lighten-3" light height="45">
      <template v-slot:prepend>
        <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      </template>
      <template v-slot:append>
        <v-avatar size="32px"
          ><v-img
            src="https://miro.medium.com/v2/resize:fit:1000/0*YISbBYJg5hkJGcQd.png"
          >
          </v-img
        ></v-avatar>
      </template>
      <v-toolbar-title>{{ title }}</v-toolbar-title>
    </v-app-bar>

    <!-- Navigation Drawer -->
    <v-navigation-drawer
      v-model="drawer"
      app
      color="grey-lighten-2"
      :elevation="4"
    >
      <v-list dense>
        <v-list-item
          prepend-avatar="https://miro.medium.com/v2/resize:fit:1000/0*YISbBYJg5hkJGcQd.png"
          subtitle="user@gmailcom"
          title="Usuário"
        ></v-list-item>
      </v-list>

      <v-divider></v-divider>

      <v-list density="compact" nav>
        <v-list-item
          prepend-icon="mdi-folder"
          title="My Files"
          value="myfiles"
        ></v-list-item>
        <v-list-item
          prepend-icon="mdi-account-multiple"
          title="Shared with me"
          value="shared"
        ></v-list-item>
        <v-list-item
          prepend-icon="mdi-star"
          title="Starred"
          value="starred"
        ></v-list-item>
      </v-list>
      <v-spacer />
      <!-- Botão Logout -->
      <template v-slot:append>
        <div class="pa-2 mb-3">
          <v-btn block color="primary" :elevation="5" rounded="lg">
            Logout
          </v-btn>
        </div>
      </template>
    </v-navigation-drawer>

    <!-- Main Content -->
    <v-main>
      <v-container>
        <slot></slot>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "Culture Verse",
    },
  },
  data() {
    return {
      drawer: false,
    };
  },
};
</script>

<style scoped>
h1 {
  margin-top: 20px;
}
</style>
