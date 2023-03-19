<template>
  <div class="bannerbg-2 font-style">
    <v-overlay v-model="overlayMobile" z-index="99999999" opacity="1">
      Ce site n'es pas dispo sur mobile,<br />
      Venez nous découvrir sur un ordinateur !
    </v-overlay>
    <v-btn
      class="back-btn"
      style="
        position: absolute;
        top: 30px;
        left: 30px;
        font-size: 1.05rem;

        font-weight: bold;
      "
      @click="$router.push('/')"
    >
      <v-icon style="padding-right: 5px">
        mdi-arrow-left-bold-circle-outline
      </v-icon>
      RETOUR
    </v-btn>

    <v-row class="banner d-flex align-center justify-center">
      <v-img
        max-height="300"
        contain
        :src="require('~/assets/logo-rio.png')"
      ></v-img>
    </v-row>
    <transition name="fade" mode="out-in">
      <v-row
        v-if="activeChapter === ''"
        key="1"
        class="banner2 d-flex align-center justify-center"
        style="padding: 25px"
      >
        <v-col>
          <v-col
            style="
              display: flex;
              justify-content: center;
              align-items: center;
              position: relative;
            "
          >
            <div
              class="circle blue__circle"
              :class="blueChapterActive ? 'active_blue__circle' : null"
              @click="
                activeChapter = 'blue'
                blueChapterActive = true
              "
            >
              <v-card-title v-if="!blueChapterActive" class="blue__text"
                >Chapitre 1</v-card-title
              >
            </div>
            <div
              class="circle black__circle"
              :class="blackChapterActive ? 'active_black__circle' : null"
              @click="
                activeChapter = 'black'
                blackChapterActive = true
              "
            >
              <v-card-title v-if="!blackChapterActive" class="black__text"
                >Chapitre 2</v-card-title
              >
            </div>
            <div
              class="circle red__circle"
              :class="redChapterActive ? 'active_red__circle' : null"
              @click="
                activeChapter = 'red'
                redChapterActive = true
              "
            >
              <v-card-title v-if="!redChapterActive" class="red__text"
                >Chapitre 3</v-card-title
              >
            </div>
          </v-col>
          <v-col
            style="
              display: flex;
              justify-content: center;
              align-items: center;
              bottom: 150px;
              position: absolute;
            "
          >
            <div
              class="circle yellow__circle"
              :class="yellowChapterActive ? 'active_yellow__circle' : null"
              @click="
                activeChapter = 'yellow'
                yellowChapterActive = true
              "
            >
              <v-card-title v-if="!yellowChapterActive" class="yellow__text"
                >Chapitre 4</v-card-title
              >
            </div>
            <div
              class="circle green__circle"
              :class="greenChapterActive ? 'active_green__circle' : null"
              @click="
                activeChapter = 'green'
                greenChapterActive = true
              "
            >
              <v-card-title v-if="!greenChapterActive" class="green__text"
                >Chapitre 5</v-card-title
              >
            </div>
          </v-col>
        </v-col>
      </v-row>
      <v-row
        v-else
        key="2"
        class="banner2"
        style="padding: 25px; position: relative"
        :class="activeChapterStyle"
      >
        <v-btn
          icon
          style="
            position: absolute;
            top: 20px;
            right: 30px;
            z-index: 99999999;
            color: white;
          "
          @click="activeChapter = ''"
        >
          <v-icon size="44"> mdi-close-circle-outline </v-icon>
        </v-btn>
        <v-col>
          <v-col
            style="
              display: flex;
              justify-content: center;
              align-items: center;
              position: relative;
            "
          >
            <v-card-title
              style="position: absolute; color: white; font-weight: bold"
              :style="activeChapterPositionTitle"
            >
              {{ activeChapterTitle }}
            </v-card-title>
            <v-card-text
              style="
                position: absolute;
                color: white;
                width: 700px;
                font-size: 1.25em;
                white-space: pre-line;
              "
              :style="activeChapterPositionText"
            >
              {{ activeChapterText }}
            </v-card-text>
            <div
              class="circle white__circle"
              :style="activeChapter === 'blue' ? '' : 'opacity: 0'"
              @click="activeChapter === 'blue' ? (activeChapter = '') : null"
            >
              <v-avatar size="290">
                <v-img :src="require(`~/assets/rio/chap1.jpg`)" />
              </v-avatar>
            </div>
            <div
              class="circle white__circle"
              :style="'opacity: 0'"
              @click="activeChapter === 'black' ? (activeChapter = '') : null"
            >
              <v-avatar size="290">
                <v-img :src="require(`~/assets/rio/chap2.jpg`)" />
              </v-avatar>
            </div>
            <div
              class="circle white__circle"
              :style="activeChapter === 'red' ? '' : 'opacity: 0'"
              @click="activeChapter === 'red' ? (activeChapter = '') : null"
            >
              <v-avatar size="290">
                <v-img :src="require(`~/assets/rio/chap3.jpg`)" />
              </v-avatar>
            </div>
          </v-col>
          <v-col
            style="
              display: flex;
              justify-content: center;
              align-items: center;
              bottom: 150px;
              position: absolute;
            "
          >
            <div
              class="circle white__circle"
              :style="activeChapter === 'yellow' ? '' : 'opacity: 0'"
              @click="activeChapter === 'yellow' ? (activeChapter = '') : null"
            >
              <v-avatar size="290">
                <v-img :src="require(`~/assets/chap4.jpg`)" />
              </v-avatar>
            </div>
            <div
              class="circle white__circle"
              :style="activeChapter === 'green' ? '' : 'opacity: 0'"
              @click="activeChapter === 'green' ? (activeChapter = '') : null"
            >
              <v-avatar size="290">
                <v-img :src="require(`~/assets/chap5.jpg`)" />
              </v-avatar>
            </div>
          </v-col>
        </v-col>
      </v-row>
    </transition>
    <v-row
      style="
        display: flex;
        justify-content: center;
        align-items: center;
        margin-bottom: 25px;
      "
    >
      <v-btn
        large
        class="next-btn"
        style="margin-top: 25px; font-size: 1.25rem; font-weight: bold"
        @click="$router.push('tokyo')"
      >
        TOKYO
        <v-icon style="padding-left: 5px">
          mdi-arrow-right-bold-circle-outline
        </v-icon>
      </v-btn>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeChapter: '',
      blueChapterActive: false,
      redChapterActive: false,
      greenChapterActive: false,
      yellowChapterActive: false,
      blackChapterActive: false
    }
  },
  computed: {
    activeChapterStyle() {
      if (this.activeChapter === 'blue') {
        return 'blue__bg'
      } else if (this.activeChapter === 'red') {
        return 'red__bg'
      } else if (this.activeChapter === 'green') {
        return 'green__bg'
      } else if (this.activeChapter === 'yellow') {
        return 'yellow__bg'
      } else {
        return 'black__bg'
      }
    },
    activeChapterPositionTitle() {
      if (this.activeChapter === 'blue') {
        return 'top: 10px; right: 150px'
      } else if (this.activeChapter === 'red') {
        return 'top: 10px; left: 10px'
      } else if (this.activeChapter === 'green') {
        return 'top: 10px; left: 10px'
      } else if (this.activeChapter === 'yellow') {
        return 'top: 50px; left: 10px'
      } else {
        return 'top: 80px; right: 250px'
      }
    },
    activeChapterPositionText() {
      if (this.activeChapter === 'blue') {
        return 'top: 120px; right: 100px'
      } else if (this.activeChapter === 'red') {
        return 'top: 120px; left: 10px'
      } else if (this.activeChapter === 'green') {
        return 'top: 120px; left: 10px'
      } else if (this.activeChapter === 'yellow') {
        return 'top: 70px; right: -50px'
      } else {
        return 'top: 10px; left: 10px'
      }
    },
    activeChapterText() {
      if (this.activeChapter === 'blue') {
        return `
        La ville de Rio de Janeiro a décidé de se porter candidate à l’accueil d’un tel évènement afin de faire rayonner davantage le pays.
        
        Mais aussi pour faire suite à l’organisation de la Coupe du Monde de football de 2014 qui s’est déroulée au Brésil.`
      } else if (this.activeChapter === 'red') {
        return `
        Marcelo Pedroso, président de l’autorité olympique publique, qui a pour mission de surveiller les dépenses pour les JO de Rio. 
        
        L’état régional annonce en juin 2016: 
        
        l’état de calamité publique => état peut adopter des mesures exceptionnelles nécessaires à la rationalisation des services publics essentiels pour réaliser les JO. (exemple: le traitement des fonctionnaires)`
      } else if (this.activeChapter === 'green') {
        return `
        Site officiel du CIO 
        
        Articles de presse 
        `
      } else if (this.activeChapter === 'yellow') {
        return `
        Le budget final s’est élevé à la fin des jeux à plus de 13 milliards d’euros 
        
        Perte dû notamment aux éléphants blancs qui sont des infrastructures à l’abandon
        `
      } else {
        return `
        Le budget initial dans le dossier de candidature était de 9 milliards d’euros
          
          Les principaux contributeurs: 
          
            Le comité international olympique a aidé le comité chargé de l’organisation des jeux olympiques brésilien à hauteur d’environ 1,5 milliards d’euros
          
            Le gouvernement brésilien a investi dans la construction et la rénovation d’installations sportives mais aussi dans les moyens de transport et les dispositifs de sécurité

            Les sponsors officiels

          Les principales dépenses: 

            Les infrastructures sportives: rénovation stade Maracana 
            
            La sécurité: la délinquance  
            
            Les transports publics pour les touristes et les navettes pour transporter les athlètes sur les sites etc. `
      }
    },
    activeChapterTitle() {
      if (this.activeChapter === 'blue') {
        return 'Chapitre 1 : Le saviez-vous ?'
      } else if (this.activeChapter === 'red') {
        return 'Chapitre 3 : Le contrôle du budget'
      } else if (this.activeChapter === 'green') {
        return 'Chapitre 5 : Principales sources'
      } else if (this.activeChapter === 'yellow') {
        return 'Chapitre 4 : Perte ou gain financier ?'
      } else {
        return 'Chapitre 2 : L’organisation de l’évènement'
      }
    },
    overlayMobile() {
      if (this.$device.isMobile) {
        console.log('true')
        return true
      } else {
        console.log('false')
        return false
      }
    }
  },
  methods: {}
}
</script>

<style>
.back-btn {
  background-color: #c95050 !important;
  color: white !important;
}
.next-btn {
  background-color: #50c965 !important;
  color: white !important;
}
.banner {
  height: 500px;
  display: flex;
  justify-content: center;
  /* background-image: url(~/assets/banner-bg2.jpg); */
  align-items: center;
  background-size: cover;
}
.bannerbg-2 {
  background-image: url(~/assets/banner-bg2.jpg);

  background-size: cover;
}

.font-style {
  font-family: 'Montserrat', sans-serif;
}

.banner2 {
  display: flex;
  height: 650px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.light-bg {
  background-color: lightgoldenrodyellow;
}

.circle {
  height: 300px;
  width: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  z-index: 999;
  margin: 0 10px 0 10px;
}

.black__circle {
  background-color: #1e1e1e;
}
.black__bg {
  background-color: #1e1e1e;
}
.black__circle:hover {
  background: white;
  border: solid 10px #1e1e1e;
}
.active_black__circle {
  background: white;
  border: solid 10px #1e1e1e;
}
.black__text {
  color: #1e1e1e;
}

.yellow__circle {
  background-color: #f4b33d;
}
.yellow__bg {
  background-color: #f4b33d;
}
.yellow__circle:hover {
  background: white;
  border: solid 10px #f4b33d;
}
.active_yellow__circle {
  background: white;
  border: solid 10px #f4b33d;
}
.yellow__text {
  color: #f4b33d;
}

.blue__circle {
  background-color: #0083c8;
}
.blue__bg {
  background-color: #0083c8;
}

.blue__circle:hover {
  background: white;
  border: solid 10px #0083c8;
}

.active_blue__circle {
  background: white;
  border: solid 10px #0083c8;
}

.blue__text {
  color: #0083c8;
}

.white__circle {
  border: solid 10px white;
  background-color: transparent;
}
.white__circle:hover {
  background: transparent;
}

.white__text {
  color: white;
}

.red__circle {
  background-color: #e9354e;
}

.red__bg {
  background-color: #e9354e;
}

.red__circle:hover {
  background: white;
  border: solid 10px #e9354e;
}
.active_red__circle {
  background: white;
  border: solid 10px #e9354e;
}
.red__text {
  color: #e9354e;
}

.green__circle {
  background-color: #00a851;
}

.green__bg {
  background-color: #00a851;
}

.green__circle:hover {
  background: white;
  border: solid 10px #00a851;
}
.active_green__circle {
  background: white;
  border: solid 10px #00a851;
}
.green__text {
  color: #00a851;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}

.fade-enter,
.fade-leave-active {
  opacity: 0;
}
</style>
