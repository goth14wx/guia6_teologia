<template>
  <v-app>
    <v-app-bar
      :clipped-left="false"
      app
      fixed
      light
    >
    <v-spacer></v-spacer>
      <v-toolbar-title v-text="title" class="text-center font-raleway" />
      <v-spacer></v-spacer>
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer
      :fixed="true"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      title: 'Linea de tiempo'
    }
  }
}
</script>
