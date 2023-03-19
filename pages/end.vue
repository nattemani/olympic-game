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
          <v-card-title class="intro-title"> CONCLUSION </v-card-title>
          <v-card-text class="intro-text">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam
            sagittis porta elit a ornare. Praesent suscipit, nibh sed iaculis
            convallis, nunc nunc eleifend odio, ut pellentesque mauris ipsum non
            lectus. Suspendisse ac pretium diam. Sed pharetra mi id sapien
            faucibus imperdiet. Donec imperdiet pharetra mauris at feugiat.
            Maecenas mollis gravida augue eget suscipit. Maecenas ut justo in
            nunc accumsan cursus ac aliquam magna. Vestibulum ante ipsum primis
            in faucibus orci luctus et ultrices posuere cubilia curae; Mauris
            imperdiet volutpat dolor eget eleifend. Nulla faucibus pellentesque
            neque sed tincidunt. In id velit at odio consectetur laoreet. Donec
            a odio ac tellus lobortis elementum. In eget luctus quam. Donec a
            ultrices lacus. Vestibulum a nisi quis dui ultricies maximus. Lorem
            ipsum dolor sit amet, consectetur adipiscing elit.</v-card-text
          >
        </v-card>
      </v-col>
    </v-row>

    <v-row style="display: flex; justify-content: center; align-items: center">
      <v-card
        flat
        style="display: flex; flex-direction: column; align-items: center"
      >
        <v-card-title> Réalisé par : </v-card-title>
        <v-card-subtitle> Fatoumagrande, et des gens...</v-card-subtitle>
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
  width: 80%;
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
