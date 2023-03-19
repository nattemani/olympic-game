<template>
  <div class="bannerbg-3 font-style">
    <v-overlay v-model="overlayMobile" z-index="99999999" opacity="1">
      Ce site n'es pas dispo sur mobile,<br />
      Venez nous découvrir sur un ordinateur !
    </v-overlay>
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
          <v-card-title class="intro-title">
            La gouvernance financière et budgétaire des Jeux Olympiques
          </v-card-title>
          <v-card-text class="intro-text">
            Les Jeux Olympiques modernes ont été initiés par le baron Pierre de Coubertin et sont devenus l’un des évènements sportifs les plus emblématiques
            </br></br>Au-delàs de l’aspect sportif c’est aussi un moyen de faire rayonner culturellement un pays et de montrer sa puissance.
            </br></br>Cependant, pour pouvoir témoigner d’une telle influence encore faut-il pouvoir avoir la capacité financière d’organiser ce « méga évènement ».
            </br></br>En effet, pour pouvoir organiser un tel évènement il convient de prévoir un budget adapté.
            </br></br>Au regard de l’importance de cet évènement mais aussi des coûts qu’il engendre, la question qui se pose naturellement est de savoir si l’organisation des JO est in fine un gain ou une perte financière pour le pays hôte ?
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="10" style="display: flex">
        <v-col>
          <v-card height="200" style="position: relative">
            <v-container>
              <v-row>
                <v-col cols="8">
                  <v-card-title style="font-weight: bold"> RIO </v-card-title>
                  <v-card-text>
                    Les premiers jeux d'Amérique du sud
                  </v-card-text>
                </v-col>
                <v-col>
                  <v-avatar
                    style="position: absolute; top: 20px; right: 20px"
                    size="70"
                  >
                    <v-img :src="require(`~/assets/rio-avatar.jpg`)"> </v-img>
                  </v-avatar>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-col>
        <v-col>
          <v-card height="200" style="position: relative">
            <v-container>
              <v-row>
                <v-col cols="8">
                  <v-card-title style="font-weight: bold"> TOKYO </v-card-title>
                  <v-card-text>
                    Les jeux à huit clos
                  </v-card-text>
                </v-col>
                <v-col>
                  <v-avatar
                    style="position: absolute; top: 20px; right: 20px"
                    size="70"
                  >
                    <v-img :src="require(`~/assets/tokyo-avatar.jpg`)"> </v-img>
                  </v-avatar>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-col>
        <v-col>
          <v-card height="200" style="position: relative">
            <v-container>
              <v-row>
                <v-col cols="8">
                  <v-card-title style="font-weight: bold"> PARIS </v-card-title>
                  <v-card-text>
                    Les premiers jeux d'ambition environnementale
                  </v-card-text>
                </v-col>
                <v-col>
                  <v-avatar
                    style="position: absolute; top: 20px; right: 20px"
                    size="70"
                  >
                    <v-img :src="require(`~/assets/paris-avatar.jpeg`)">
                    </v-img>
                  </v-avatar>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-col>
      </v-col>
      <v-col cols="8" style="margin: 10px 0px 10px 0px">
        <v-btn
          block
          large
          style="font-weight: bold"
          class="start-btn"
          @click="$router.push('/rio')"
        >
          COMMENCER
        </v-btn>
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
