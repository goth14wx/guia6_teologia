<template>
    <v-timeline :dense="$vuetify.breakpoint.smAndDown">
    <v-timeline-item v-for="(seccion,i) in secciones" :key="i"
        :data-aos="`flip-${flip[Math.floor(Math.random()*4)]}`"
        data-aos-delay="500"
      fill-dot
      :right="i%2!=0"
      :left="i%2==0"
      :small="true"
    >
          <template v-slot:icon>
        <v-avatar>
          <img src="https://cdn4.iconfinder.com/data/icons/christmas-2233/64/bible-christian-book-cultures-christianity-512.png">
        </v-avatar>
      </template>
    <template v-slot:opposite>
        <a :href="seccion.link" target="_blank">
        <span
          :class="`white--text font-quicksand`"
          v-text="seccion.versiculo"
        ></span>
        </a>
    </template>
    <v-hover v-slot:default="{ hover }">
      <v-card>
                <!--HOVER-->

        <v-expand-transition>
          <div
            v-if="hover"
            class="d-flex transition-fast-in-fast-out darken-2 v-card--reveal font-quicksand white--text"
            :class="seccion.color_card"
            style="height: 100%;"
          >
           "{{explicaciones[seccion.versiculoExplicacion]}}"
          </div>
        </v-expand-transition>
        <v-card-title :class="seccion.color_card">
          <v-icon
            dark
            size="42"
            class="mr-4"
          >
            mdi-lock-open
          </v-icon>
          <h2 class="white--text font-weight-light font-raleway">{{seccion.titulo_seccion}}</h2>
        </v-card-title>
        <v-container>
          <v-row>
            <v-col cols="9" md="9" class="font-montalternates">
              {{seccion.Texto}}
            </v-col>
            <v-col
              class="hidden-sm-and-down text-right"
              md="3"
            >
              <img width="100px" :src="seccion.img"/>
            </v-col>
          </v-row>
        </v-container>


      </v-card>
      </v-hover>
    </v-timeline-item>
  </v-timeline>
</template>

<script>
import seccionesJson from "@/static/secciones.json";
import explicaciones from "@/static/explicaciones.json";
export default {
  data:()=>({
    secciones:seccionesJson.secciones,
    explicaciones:explicaciones.explicaciones,
    flip:[
      "left",
      "right",
      "down",
      "up"
    ]
  })
}
</script>


<style>
.v-card--reveal {
  align-items: center;
  bottom: 0;
  justify-content: center;
  position: absolute;
  width: 100%;
}
</style>
