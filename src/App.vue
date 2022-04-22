<template>
  <v-app id="inspire">
    <v-navigation-drawer app v-model="drawer">
      <v-list dense>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-home</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Realizar Teste</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-contact-mail</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Contato</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app color="indigo" dark>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>Fuxiqueira</v-toolbar-title>
    </v-app-bar>

    <v-content>
      <v-container class="fill-height" fluid>
        <template>
          <v-progress-linear value="15"></v-progress-linear>
        </template>

        <v-row height="100%">
          <v-col>
            <v-carousel
              :continuous="false"
              :show-arrows="false"
              :progress="false"
              :cycle="false"
              height="100%"
              hide-delimiters
              hide-delimiter-background
              v-model="model"
            >
              <v-carousel-item :key="i" v-for="(questao, i) in questoes">
                <questao
                  :titulo="questao.titulo"
                  :descricao="questao.descricao"
                  :alternativas="questao.alternativas"
                  :imagem="questao.imagem"
                  :audio="questao.audio"
                  v-bind:responder="addResposta"
                ></questao>
              </v-carousel-item>
            </v-carousel>
          </v-col>
        </v-row>
      </v-container>
    </v-content>
    <v-footer app color="indigo">
      <span class="white--text">&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
import Questao from "@/components/Questao.vue";
import QUESTOES from "@/data/questoes.js";

export default {
  props: {
    source: String,
  },

  components: {
    questao: Questao,
  },
  computed: {
    active() {
      return 0;
    },
  },
  mounted() {},
  data: () => ({
    model: 0,
    drawer: null,
    respostas: [],
    colors: ["indigo", "warning", "pink darken-2", "red lighten-1", "deep-purple accent-4"],

    questoes: QUESTOES,
  }),
  methods: {
    addResposta(resp) {
      this.respostas.push(resp);
      this.nextItem();
    },
    nextItem() {
      this.model += 1;
    },
  },
};
</script>
