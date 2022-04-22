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
import Questao from '@/components/Questao.vue';
import bolacha from '@/assets/img/14bolacha.jpg';
import mixirica1 from '@/assets/img/3mixirica1.jpeg';
import tucano from '@/assets/img/17tucano.jpg';
import besouro from '@/assets/img/18besouro.jpg';
import laranjinha from '@/assets/img/4laranjinha.png';
import drinkglassmilkwallpaperpreview from '@/assets/img/20drinkglassmilkwallpaperpreview.jpg';
import biloca from '@/assets/img/5biloca.jpeg';
// import solidgreenbackground from '@/assets/img/21solidgreenbackground.jpeg';
import paofrances from '@/assets/img/7paofrances.jpg';
// import mandioca from '@/assets/img/25mandioca.jpeg';

import mp3file20a from '@/assets/audio/20a.mp3';
// import mp3file16b from '@/assets/audio/16b.mp3';
// import mp3file16c from '@/assets/audio/16c.mp3';
// import mp3file16d from '@/assets/audio/16d.mp3';
// import mp3file16e from '@/assets/audio/16e.mp3';
import mp3file19a from '@/assets/audio/19a.mp3';
// import mp3file19b from '@/assets/audio/19b.mp3';
// import mp3file19c from '@/assets/audio/19c.mp3';
// import mp3file19d from '@/assets/audio/19d.mp3';
// import mp3file19e from '@/assets/audio/19e.mp3';
// import mp3file19f from '@/assets/audio/19f.mp3';
// import mp3file19g from '@/assets/audio/19g.mp3';
// import mp3file19h from '@/assets/audio/19h.mp3';
// import mp3file19i from '@/assets/audio/19i.mp3';
// import mp3file19j from '@/assets/audio/19j.mp3';

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
    colors: ['indigo', 'warning', 'pink darken-2', 'red lighten-1', 'deep-purple accent-4'],

    questoes: [
      {
        titulo: 'Questao 1',
        descricao:
          'Além de menino, qual outra forma de chamar uma criança entre 5 e 10 anos, do sexo masculino?',
        alternativas: [
          {
            letra: 'a',
            descricao: 'Garoto',
          },

          {
            letra: 'b',
            descricao: 'Moleque',
          },

          {
            letra: 'c',
            descricao: 'Guri',
          },

          {
            letra: 'd',
            descricao: 'Piá',
          },

          {
            letra: 'e',
            descricao: 'Rapazinho',
          },

          {
            letra: 'f',
            descricao: 'Homenzinho',
          },

          {
            letra: 'g',
            descricao: 'Pivete',
          },

          {
            letra: 'h',
            descricao: 'Pirralho',
          },

          {
            letra: 'i',
            descricao: 'Bambino',
          },

          {
            letra: 'j',
            descricao: 'Bacuri',
          },

          {
            letra: 'k',
            descricao: 'Curumim',
          },

          {
            letra: 'l',
            descricao: 'Badeco',
          },

          {
            letra: 'm',
            descricao: 'Pixote',
          },

          {
            letra: 'n',
            descricao: 'Criança',
          },

          {
            letra: 'o',
            descricao: 'Pimpolho',
          },

          {
            letra: 'p',
            descricao: 'Pequeno',
          },

          {
            letra: 'q',
            descricao: 'Nenhuma',
          },
        ],
      },
      {
        titulo: 'Questao 2',
        descricao: 'Como se chama um rio pequeno, de uns dois metros de largura?',
        alternativas: [
          {
            letra: 'a',
            descricao: 'Igarapé',
          },

          {
            letra: 'b',
            descricao: 'Garapé',
          },

          {
            letra: 'c',
            descricao: 'Corixo',
          },

          {
            letra: 'd',
            descricao: 'Corgo / Corguinho',
          },

          {
            letra: 'e',
            descricao: 'Córrego',
          },

          {
            letra: 'f',
            descricao: 'Riacho / Riachinho / Riachozinho',
          },

          {
            letra: 'g',
            descricao: 'Riozinho',
          },

          {
            letra: 'h',
            descricao: 'Ribeirão',
          },

          {
            letra: 'i',
            descricao: 'Sanga / Sanguinha ',
          },

          {
            letra: 'j',
            descricao: 'Rego/Reguinho',
          },

          {
            letra: 'k',
            descricao: 'Arroio',
          },

          {
            letra: 'l',
            descricao: 'Açude',
          },

          {
            letra: 'm',
            descricao: 'Barreiro',
          },

          {
            letra: 'n',
            descricao: 'Brejo',
          },

          {
            letra: 'o',
            descricao: 'Canal',
          },

          {
            letra: 'p',
            descricao: 'Bisca',
          },

          {
            letra: 'q',
            descricao: 'Cachoeira / Cachoeirinha',
          },
          {
            letra: 'r',
            descricao: 'Lagoa',
          },
          {
            letra: 's',
            descricao: 'Lago',
          },
          {
            letra: 't',
            descricao: 'Vala/Valo/Valão',
          },
          {
            letra: 'u',
            descricao: 'Valeta/Valetinha',
          },
          {
            letra: 'v',
            descricao: 'Grota / Grotão',
          },
          {
            letra: 'w',
            descricao: 'Olheirinho',
          },
          {
            letra: 'x',
            descricao: 'Correnteza / Corrente',
          },
          {
            letra: 'y',
            descricao: 'Fonte / Fontezinha',
          },
          {
            letra: 'z',
            descricao: 'Baixa',
          },
          {
            letra: 'aa',
            descricao: 'Baixio',
          },
          {
            letra: 'bb',
            descricao: 'Estreito',
          },
          {
            letra: 'cc',
            descricao: 'Enseada',
          },
          {
            letra: 'dd',
            descricao: 'Cóligo',
          },
          {
            letra: 'ee',
            descricao: 'Vazante',
          },
          {
            letra: 'ff',
            descricao: 'Lajeado',
          },
          {
            letra: 'gg',
            descricao: 'Vertente',
          },
        ],
      },
      {
        titulo: 'Questao 3',
        descricao: 'Independente da variedade, qual o nome das frutas das fotos?',
        imagem: mixirica1,
        alternativas: [
          {
            letra: 'a',
            descricao: 'Mimosa',
          },

          {
            letra: 'b',
            descricao: 'Tanja',
          },

          {
            letra: 'c',
            descricao: 'Mexerica / Mixirica',
          },

          {
            letra: 'd',
            descricao: 'Poncã / Ponkã',
          },

          {
            letra: 'e',
            descricao: 'Pocã / Pokan',
          },

          {
            letra: 'f',
            descricao: 'Tangerina',
          },

          {
            letra: 'g',
            descricao: 'Bergamota / Vergamota',
          },

          {
            letra: 'h',
            descricao: 'Laranja-cravo',
          },

          {
            letra: 'i',
            descricao: 'Laranja-crava',
          },

          {
            letra: 'j',
            descricao: 'Mangota (Mangote, Mongote, Margota)',
          },

          {
            letra: 'k',
            descricao: 'Morgota',
          },

          {
            letra: 'l',
            descricao: 'Fuxiqueira',
          },

          {
            letra: 'm',
            descricao: 'Mandarina',
          },

          {
            letra: 'n',
            descricao: 'Carioquinha',
          },

          {
            letra: 'o',
            descricao: 'Maricota/Maricote',
          },

          {
            letra: 'p',
            descricao: 'Muricota/Moricota (Muricote, Morocota, Morocote)',
          },

          {
            letra: 'q',
            descricao: 'Murcote/Morcote (Marcota, Morcota, Mucote)',
          },
          {
            letra: 'r',
            descricao: 'Mimo-do-céu',
          },
          {
            letra: 's',
            descricao: 'Mixiriquêra',
          },
          {
            letra: 't',
            descricao: 'Azedinha',
          },
          {
            letra: 'u',
            descricao: 'Mormota',
          },
          {
            letra: 'v',
            descricao: 'Irredera /Enredera',
          },
          {
            letra: 'w',
            descricao: 'Clementina',
          },
        ],
      },
      {
        titulo: 'Questao 4',
        descricao: 'Qual o nome desse suco de frutas congelado em saquinhos? ',
        imagem: laranjinha,
        alternativas: [
          {
            letra: 'a',
            descricao: 'Brasinha',
          },

          {
            letra: 'b',
            descricao: 'Tubiba',
          },

          {
            letra: 'c',
            descricao: 'Dida',
          },

          {
            letra: 'd',
            descricao: 'Vip',
          },

          {
            letra: 'e',
            descricao: 'Sacolé',
          },

          {
            letra: 'f',
            descricao: 'Laranjinha',
          },

          {
            letra: 'g',
            descricao: 'Dindin',
          },

          {
            letra: 'h',
            descricao: 'Apolo',
          },

          {
            letra: 'i',
            descricao: 'Dudu',
          },

          {
            letra: 'j',
            descricao: 'Tabu',
          },

          {
            letra: 'k',
            descricao: 'Juju',
          },

          {
            letra: 'l',
            descricao: 'Refresco',
          },

          {
            letra: 'm',
            descricao: 'Flau / Frau',
          },

          {
            letra: 'n',
            descricao: 'Chupe-chupe / Chup-chup',
          },

          {
            letra: 'o',
            descricao: 'Gelinho',
          },

          {
            letra: 'p',
            descricao: 'Geladinho',
          },

          {
            letra: 'q',
            descricao: 'Geladinha',
          },

          {
            letra: 'r',
            descricao: 'Picolé',
          },

          {
            letra: 's',
            descricao: 'Chopp',
          },

          {
            letra: 't',
            descricao: 'Chope',
          },

          {
            letra: 'u',
            descricao: 'Suquinho',
          },

          {
            letra: 'v',
            descricao: 'Bolão',
          },
        ],
      },
      {
        titulo: 'Questao 5',
        descricao: 'Qual é outro nome para “Bolinha de gude”?',
        imagem: biloca,
        alternativas: [
          {
            letra: 'a',
            descricao: 'Peteca',
          },

          {
            letra: 'b',
            descricao: 'Fona / Bola de fona',
          },

          {
            letra: 'c',
            descricao: 'Butila',
          },

          {
            letra: 'd',
            descricao: 'Tila-tila',
          },

          {
            letra: 'e',
            descricao: 'Gurca / Gurquinha',
          },

          {
            letra: 'f',
            descricao: 'China',
          },

          {
            letra: 'g',
            descricao: 'Bolita',
          },

          {
            letra: 'h',
            descricao: 'Bulita',
          },

          {
            letra: 'i',
            descricao: 'Bolica',
          },

          {
            letra: 'j',
            descricao: 'Bulica / Búlica',
          },

          {
            letra: 'k',
            descricao: 'Burica / Búrica',
          },

          {
            letra: 'l',
            descricao: 'Burca / Burquinha',
          },

          {
            letra: 'm',
            descricao: 'Quilica',
          },

          {
            letra: 'n',
            descricao: 'Clica',
          },

          {
            letra: 'o',
            descricao: 'Peca',
          },

          {
            letra: 'p',
            descricao: 'Biloca',
          },

          {
            letra: 'q',
            descricao: 'Bilisco',
          },

          {
            letra: 'r',
            descricao: 'Biroca',
          },

          {
            letra: 's',
            descricao: 'Birosca',
          },

          {
            letra: 't',
            descricao: 'Bilosca',
          },

          {
            letra: 'u',
            descricao: 'Birola',
          },

          {
            letra: 'v',
            descricao: 'Biroquê',
          },

          {
            letra: 'w',
            descricao: 'Gude',
          },

          {
            letra: 'x',
            descricao: 'Bila',
          },

          {
            letra: 'y',
            descricao: 'Ximbra / Chimbra',
          },
          {
            letra: 'z',
            descricao: 'Fubeca',
          },
          {
            letra: 'aa',
            descricao: 'Boleba/ Baleba',
          },
          {
            letra: 'bb',
            descricao: 'Bolinha de crica / Bolinha de crique',
          },
          {
            letra: 'cc',
            descricao: 'Pinica',
          },
          {
            letra: 'dd',
            descricao: 'Pilica/Tilica',
          },
          {
            letra: 'ee',
            descricao: 'Aço',
          },
          {
            letra: 'ff',
            descricao: 'Marraio',
          },
          {
            letra: 'gg',
            descricao: 'Bolinha de vidro',
          },
          {
            letra: 'hh',
            descricao: 'Bolinha',
          },
          {
            letra: 'ii',
            descricao: 'Olho de gato',
          },
          {
            letra: 'jj',
            descricao: 'Peloco',
          },
          {
            letra: 'kk',
            descricao: 'Nenhuma',
          },
        ],
      },
      {
        titulo: 'Questao 6',
        descricao: 'Qual interjeição você mais usa?',
        alternativas: [
          {
            letra: 'a',
            descricao: 'Ôxe',
          },

          {
            letra: 'b',
            descricao: 'Oxente',
          },

          {
            letra: 'c',
            descricao: 'Uai',
          },

          {
            letra: 'd',
            descricao: 'Báh',
          },

          {
            letra: 'e',
            descricao: 'Tchê',
          },

          {
            letra: 'f',
            descricao: 'Égua',
          },

          {
            letra: 'g',
            descricao: 'Arre égua',
          },

          {
            letra: 'h',
            descricao: 'Hehein',
          },

          {
            letra: 'i',
            descricao: 'Afe / Aff',
          },

          {
            letra: 'j',
            descricao: 'Vei / Véi / Veio',
          },

          {
            letra: 'k',
            descricao: 'Vichi / Vixe',
          },

          {
            letra: 'l',
            descricao: 'Ixe',
          },

          {
            letra: 'm',
            descricao: 'Eita / Eta',
          },

          {
            letra: 'n',
            descricao: 'Meu',
          },

          {
            letra: 'o',
            descricao: 'Caraca',
          },

          {
            letra: 'p',
            descricao: 'Putz',
          },

          {
            letra: 'q',
            descricao: 'Ué',
          },

          {
            letra: 'r',
            descricao: 'Daí',
          },

          {
            letra: 's',
            descricao: 'Mano',
          },

          {
            letra: 't',
            descricao: 'Viu',
          },

          {
            letra: 'u',
            descricao: 'Valha',
          },

          {
            letra: 'v',
            descricao: 'Beí / Bei',
          },

          {
            letra: 'w',
            descricao: 'Nenhuma',
          },
        ],
      },
      {
        titulo: 'Questao 7',
        descricao: 'Como se pede esse pão na padaria?',
        imagem: paofrances,
        alternativas: [
          {
            letra: 'a',
            descricao: 'Carioquinha',
          },

          {
            letra: 'b',
            descricao: 'Média',
          },

          {
            letra: 'c',
            descricao: 'Pão francês',
          },

          {
            letra: 'd',
            descricao: 'Pão de sal',
          },

          {
            letra: 'e',
            descricao: 'Pão de trigo',
          },

          {
            letra: 'f',
            descricao: 'Pão aguado',
          },

          {
            letra: 'g',
            descricao: 'Pão d’água',
          },

          {
            letra: 'h',
            descricao: 'Pão jacó',
          },

          {
            letra: 'i',
            descricao: 'Pão massa grossa',
          },

          {
            letra: 'j',
            descricao: 'Pão careca',
          },

          {
            letra: 'k',
            descricao: 'Filão / Filãozinho',
          },

          {
            letra: 'l',
            descricao: 'Cacetinho',
          },

          {
            letra: 'm',
            descricao: 'Pãozinho',
          },

          {
            letra: 'n',
            descricao: 'Pão de padeiro',
          },

          {
            letra: 'o',
            descricao: 'Pão brotinho',
          },
        ],
      },
      {
        titulo: 'Questao 8',
        descricao:
          'A pessoa que não gosta de gastar seu dinheiro e, às vezes, até passa dificuldades para não gastar?',
        alternativas: [
          {
            letra: 'a',
            descricao: 'Roda presa',
          },

          {
            letra: 'b',
            descricao: 'Pirangueiro',
          },

          {
            letra: 'c',
            descricao: 'Canhenga',
          },

          {
            letra: 'd',
            descricao: 'Canguinha',
          },

          {
            letra: 'e',
            descricao: 'Amarrado',
          },

          {
            letra: 'f',
            descricao: 'Amarradinho',
          },

          {
            letra: 'g',
            descricao: 'Unha de fome',
          },

          {
            letra: 'h',
            descricao: 'Somítico',
          },

          {
            letra: 'i',
            descricao: 'Usurário',
          },

          {
            letra: 'j',
            descricao: 'Morta-fome',
          },

          {
            letra: 'k',
            descricao: 'Morto-de-fome',
          },

          {
            letra: 'l',
            descricao: 'Morto-a-fome',
          },

          {
            letra: 'm',
            descricao: 'Pechincheiro',
          },

          {
            letra: 'n',
            descricao: 'Agarrado',
          },

          {
            letra: 'o',
            descricao: 'Pica-fumo',
          },

          {
            letra: 'p',
            descricao: 'Arrochado',
          },

          {
            letra: 'q',
            descricao: 'Chula',
          },

          {
            letra: 'r',
            descricao: 'Fona',
          },

          {
            letra: 's',
            descricao: 'Fominha',
          },

          {
            letra: 't',
            descricao: 'Casquinha',
          },

          {
            letra: 'u',
            descricao: 'Munheca',
          },

          {
            letra: 'v',
            descricao: 'Muxiba',
          },

          {
            letra: 'w',
            descricao: 'Murrinha',
          },
          {
            letra: 'x',
            descricao: 'Miserável',
          },
          {
            letra: 'y',
            descricao: 'Tacanha',
          },
          {
            letra: 'z',
            descricao: 'Papagaio no arame',
          },
          {
            letra: 'aa',
            descricao: 'Enforcado',
          },
          {
            letra: 'bb',
            descricao: 'Muquirana',
          },
          {
            letra: 'cc',
            descricao: 'Miserento',
          },
          {
            letra: 'dd',
            descricao: 'Mão-dura',
          },
          {
            letra: 'ee',
            descricao: 'Mão-apertada',
          },
          {
            letra: 'ff',
            descricao: 'Mão-fechada',
          },
          {
            letra: 'gg',
            descricao: 'Mão de vaca',
          },
          {
            letra: 'hh',
            descricao: 'Mão de munheca',
          },
          {
            letra: 'ii',
            descricao: 'Mão de égua',
          },
          {
            letra: 'jj',
            descricao: 'Mão mirrada',
          },
          {
            letra: 'kk',
            descricao: 'Mão de figa',
          },
          {
            letra: 'll',
            descricao: 'Pão dura',
          },
          {
            letra: 'mm',
            descricao: 'Mesquinha',
          },
          {
            letra: 'nn',
            descricao: 'Avarenta',
          },
          {
            letra: 'oo',
            descricao: 'Sovina',
          },
          {
            letra: 'pp',
            descricao: 'Cainha',
          },
          {
            letra: 'qq',
            descricao: 'Ridica',
          },
        ],
      }, // Perguntas Morfossintáticas
      {
        titulo: 'Questao 9',
        descricao: 'Quando se quer saber se uma amiga está indo embora, como é que se pergunta?',
        alternativas: [
          {
            letra: 'a',
            descricao: 'Amiga, tu vais embora? ',
          },

          {
            letra: 'b',
            descricao: 'Amiga, tu vai embora? ',
          },

          {
            letra: 'c',
            descricao: 'Amiga, você vai embora?',
          },

          {
            letra: 'd',
            descricao: 'Amiga, ocê vai embora? ',
          },

          {
            letra: 'e',
            descricao: 'Amiga, cê vai embora?',
          },
        ],
      },
      {
        titulo: 'Questao 10',
        descricao: 'Quando Maria tem um livro: ',
        alternativas: [
          {
            letra: 'a',
            descricao: 'O livro de Maria',
          },

          {
            letra: 'b',
            descricao: 'O livro da Maria',
          },

          {
            letra: 'c',
            descricao: 'Ambos',
          },
        ],
      },
      {
        titulo: 'Questao 11',
        descricao: 'Quando Carlos tem um livro:',
        alternativas: [
          {
            letra: 'a',
            descricao: 'O livro do Carlos',
          },

          {
            letra: 'b',
            descricao: 'O livro de Carlos',
          },

          {
            letra: 'c',
            descricao: 'Ambos',
          },
        ],
      },
      {
        titulo: 'Questao 12',
        descricao: ' Qual o gênero de alface?',
        alternativas: [
          {
            letra: 'a',
            descricao: 'O alface',
          },

          {
            letra: 'b',
            descricao: 'A alface',
          },
        ],
      },
      {
        titulo: 'Questao 13',
        descricao: 'Um homem que rouba, você diz que é ladrão. E quando é uma mulher?',
        alternativas: [
          {
            letra: 'a',
            descricao: 'Ladrona',
          },

          {
            letra: 'b',
            descricao: 'Ladra',
          },

          {
            letra: 'c',
            descricao: 'Ladroa',
          },

          {
            letra: 'd',
            descricao: 'Gatuna',
          },
        ],
      },
      {
        titulo: 'Questao 14',
        descricao: 'Como você chama esse alimento?',

        imagem: bolacha,
        alternativas: [
          {
            letra: 'a',
            descricao: 'Biscoito',
          },

          {
            letra: 'b',
            descricao: 'Bolacha',
          },
        ],
      },
      {
        titulo: 'Questao 15',
        descricao: 'Como você conta para alguém sobre uma praça que existia no passado?',
        alternativas: [
          {
            letra: 'a',
            descricao: 'Tinha uma praça ',
          },

          {
            letra: 'b',
            descricao: 'Havia uma praça',
          },

          {
            letra: 'c',
            descricao: 'Era uma praça',
          },

          {
            letra: 'd',
            descricao: 'Via uma praça',
          },
        ],
      },
      {
        // Perguntas Fonéticas
        titulo: 'Questao 16',
        descricao: 'Como você fala o número 3?', // audio
        alternativas: [
          {
            letra: 'a',
            descricao: 'tre[js]',
          },

          {
            letra: 'b',
            descricao: 'tre[S]',
          },

          {
            letra: 'c',
            descricao: 'tre[ʃ]',
          },

          {
            letra: 'd',
            descricao: 'tre[jʃ]',
          },

          {
            letra: 'e',
            descricao: 'trei',
          },
        ],
      },
      {
        titulo: 'Questao 17',
        descricao:
          'Fale em voz alta a palavra “tomate”. A primeira silaba “to” se parece mais com quando você fala a primeira sílaba de:',

        imagem: tucano,
        alternativas: [
          {
            letra: 'a',
            descricao: 'Tucano', // imagem
          },

          {
            letra: 'b',
            descricao: 'Tomada', // imagem
          },
        ],
      },
      {
        titulo: 'Questao 18',
        descricao: 'Fale em voz alta o nome do bicho da foto. Ele rima com qual opção abaixo?',
        imagem: besouro,
        alternativas: [
          {
            letra: 'a',
            descricao: 'Touro',
          },

          {
            letra: 'b',
            descricao: 'Zorro',
          },
        ],
      },
      {
        titulo: 'Questao 19',
        descricao: 'Qual áudio representa melhor a sua pronuncia de “Pertinho”?', // audio
        alternativas: [
          {
            letra: 'a',
            descricao: 'Pe(h)(tch)inho',
            audio: mp3file19a,
          },

          {
            letra: 'b',
            descricao: 'Pe(x)(tch)inho',
            audio: mp3file19a,
          },

          {
            letra: 'c',
            descricao: 'Pe(ɽ)(tch)inho',
            audio: mp3file19a,
          },

          {
            letra: 'd',
            descricao: 'Pe(ɾ)(tch)inho',
            audio: mp3file19a,
          },

          {
            letra: 'e',
            descricao: 'Pe(ɾ)(tch)im',
            audio: mp3file19a,
          },

          {
            letra: 'f',
            descricao: 'Pe(h)(tch)im',
            audio: mp3file19a,
          },

          {
            letra: 'g',
            descricao: 'Pe(ɽ)(tch)im',
            audio: mp3file19a,
          },

          {
            letra: 'h',
            descricao: 'Pe(h)(Ti)nho',
            audio: mp3file19a,
          },

          {
            letra: 'i',
            descricao: 'Pe(r)(Ti)nho',
            audio: mp3file19a,
          },

          {
            letra: 'j',
            descricao: 'Pe(x)(TI)inho',
            audio: mp3file19a,
          },
        ],
      },
      {
        titulo: 'Questao 20',
        imagem: drinkglassmilkwallpaperpreview,
        descricao: 'Como você fala a bebida da imagem?', // audio
        audio: mp3file20a,
        alternativas: [
          {
            letra: 'a',
            descricao: 'Leiti',
          },

          {
            letra: 'b',
            descricao: 'LeitE',
          },

          {
            letra: 'c',
            descricao: 'Leitchi',
          },

          {
            letra: 'd',
            descricao: 'Leitu',
          },
        ],
      },
      {
        titulo: 'Questao 5',
        descricao: 'aaaaaaaaaaaaaaaaaa',
        alternativas: [
          {
            letra: 'a',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'b',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'c',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'd',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'e',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'f',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'g',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'h',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'i',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'j',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'k',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'l',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'm',
            descricao: 'xxxxxxxxxxxxx',
          },
        ],
      },
      {
        titulo: 'Questao 5',
        descricao: 'aaaaaaaaaaaaaaaaaa',
        alternativas: [
          {
            letra: 'a',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'b',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'c',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'd',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'e',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'f',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'g',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'h',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'i',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'j',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'k',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'l',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'm',
            descricao: 'xxxxxxxxxxxxx',
          },
        ],
      },
      {
        titulo: 'Questao 5',
        descricao: 'aaaaaaaaaaaaaaaaaa',
        alternativas: [
          {
            letra: 'a',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'b',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'c',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'd',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'e',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'f',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'g',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'h',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'i',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'j',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'k',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'l',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'm',
            descricao: 'xxxxxxxxxxxxx',
          },
        ],
      },
      {
        titulo: 'Questao 5',
        descricao: 'aaaaaaaaaaaaaaaaaa',
        alternativas: [
          {
            letra: 'a',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'b',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'c',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'd',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'e',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'f',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'g',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'h',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'i',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'j',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'k',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'l',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'm',
            descricao: 'xxxxxxxxxxxxx',
          },
        ],
      },
      {
        titulo: 'Questao 5',
        descricao: 'aaaaaaaaaaaaaaaaaa',
        alternativas: [
          {
            letra: 'a',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'b',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'c',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'd',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'e',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'f',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'g',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'h',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'i',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'j',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'k',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'l',
            descricao: 'xxxxxxxxxxxxx',
          },

          {
            letra: 'm',
            descricao: 'xxxxxxxxxxxxx',
          },
        ],
      },
    ],
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
