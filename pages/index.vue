<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
    <lineaDeTiempo/>
    </v-flex>
  </v-layout>
</template>

<script>
import lineaDeTiempo from "@/components/lineaDeTiempo.component.vue";
export default {
  components: {
    lineaDeTiempo
  }
}
</script>
