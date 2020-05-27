<template>
  <div class="top">
    <div class="linkcontainer">
      <div
        class="bg"
        :style="`background-image:url('https://api.wissehes.nl${article.image.url}')`"
        @click="openArticle"
      ></div>
      <h1 class="cover-content">{{ article.title }}</h1>
    </div>
    <v-row justify="center">
      <v-dialog v-model="dialog" fullscreen hide-overlay transition="dialog-bottom-transition">
        <v-card>
          <v-toolbar dark color="primary">
            <v-btn icon dark @click="dialog = false">
              <v-icon>mdi-close</v-icon>
            </v-btn>
            <v-toolbar-title>{{ article.title }}</v-toolbar-title>
          </v-toolbar>
          <v-container class="article">
            <div class="content">
              <VueMarkdown>{{ article.text }}</VueMarkdown>
            </div>
          </v-container>
        </v-card>
      </v-dialog>
    </v-row>
  </div>
</template>


<script>
import VueMarkdown from "vue-markdown";
export default {
  data() {
    return {
      dialog: false,
      notifications: false,
      sound: true,
      widgets: false
    };
  },
  components: {
      VueMarkdown
  },
  props: {
    article: Object
  },
  methods: {
    openArticle() {
      this.dialog = true;
    }
  }
};
</script>
<style scoped>
.article {
  padding-top: 3em;
  padding-right: 5em;
  padding-left: 5em;
}
.top {
  width: 100%;
  height: 100%;
}
.linkcontainer {
    width: 100%;
    height: 100%;
    cursor: pointer;
}
</style>