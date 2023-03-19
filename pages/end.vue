<template>
  <div class="bannerbg-3 font-style">
    <v-overlay v-model="overlayMobile" z-index="99999999" opacity="1">
      Ce site n'es pas dispo sur mobile,<br />
      Venez nous découvrir sur un ordinateur !
    </v-overlay>
    <v-btn
      style="
        position: absolute;
        top: 30px;
        left: 30px;
        font-size: 1.05rem;
        font-weight: bold;
      "
      class="back-btn"
      @click="$router.push('/')"
    >
      <v-icon style="padding-right: 5px">
        mdi-arrow-left-bold-circle-outline
      </v-icon>
      ACCUEIL
    </v-btn>
    <v-row class="banner-intro">
      <v-col
        cols="12"
        style="display: flex; align-items: center; justify-content: center"
      >
        <v-card
          style="
            background-color: #b4c3c3;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
          "
          flat
          height="450"
        >
          <v-card-title class="intro-title"> CONCLUSION </v-card-title>
          <v-card-text class="intro-text">
            Pour terminer, il est vrai que l’organisation des jeux olympiques
            fait écho à une notion : la malédiction des enchères. C’est-à-dire,
            que dans le dossier de candidature les futurs pays hôtes vont sur
            évaluer les bénéfices. In fine , l’organisation s’avère être dans
            les cas extrêmes un gouffre financier
          </br>
          </br>

            Ainsi, l’enjeu qui ressort à chaque édition est la maîtrise des
            coûts. C’est pourquoi, des solutions comme la certification des
            comptes des comités ou encore des sanctions disciplinaires en cas de
            dépassement ont émergés. Ces solutions peuvent être un remède a la
            pénurie de candidats que l’on observe depuis quelques années.
            </br>
          </br>

            Les mots de la fin => « J'ai enfreint la règle de Noé : prédire la
            pluie ne compte pas. Ce qui est important, c'est de construire des
            arches ».
        </br>Warren Buffet
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>

    <v-row style="display: flex; justify-content: center; align-items: center">
      <v-card
        flat
        style="display: flex; flex-direction: column; align-items: center"
      >
        <v-card-title> Réalisé par : </v-card-title>
        <v-card-subtitle>Fatoumata Drame (M2 FFP)</v-card-subtitle>
      </v-card>
    </v-row>
  </div>
</template>

<script>
export default {
  computed: {
    overlayMobile() {
      if (this.$device.isMobile) {
        return true
      } else {
        return false
      }
    }
  },
  methods: {}
}
</script>

<style>
.start-btn {
  background-color: #50c965 !important;
  color: white !important;
}

.back-btn {
  background-color: #c95050 !important;
  color: white !important;
}
.intro-title {
  font-size: 2em;
  margin-top: 50px;
  font-weight: bold;
}

.intro-text {
  width: 82%;
  font-size: 1.25em;
  margin-top: 50px;
}
.banner {
  display: flex;
  justify-content: center;
  /* background-image: url(~/assets/banner-bg2.jpg); */
  align-items: center;
  background-size: cover;
}

.banner-intro {
  display: flex;
  justify-content: center;
  /* background-image: url(~/assets/banner-bg2.jpg); */
  margin-top: 100px;
  align-items: center;
  height: fit-content;
  background-color: #b4c3c3;
}
.bannerbg-2 {
  background-image: url(~/assets/banner-bg2.jpg);
}
.bannerbg-3 {
  background-image: url(~/assets/banner-bg2.jpg);
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
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
