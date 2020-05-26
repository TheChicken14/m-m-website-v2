<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-btn tag="router-link" to="/" text>
        <span class="mr-2">home</span>
        <v-icon>mdi-home</v-icon>
      </v-btn>
      <v-spacer></v-spacer>
      <v-chip>Gemaakt door Wisse</v-chip>
    </v-app-bar>

    <v-content>
      <router-view />
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: "App",
};
</script>
