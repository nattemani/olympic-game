<template>
  <div class="bannerbg-2 font-style">
    <v-overlay v-model="overlayMobile" z-index="99999999" opacity="1">
      Ce site n'es pas dispo sur mobile,<br />
      Venez nous découvrir sur un ordinateur !
    </v-overlay>

    <v-row class="banner d-flex align-center justify-center">
      <v-img
        max-height="200"
        contain
        :src="require('~/assets/logo.png')"
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
        style="padding: 25px"
        :class="activeChapterStyle"
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
              class="circle white__circle"
              :style="activeChapter === 'blue' ? '' : 'opacity: 0'"
              @click="activeChapter === 'blue' ? (activeChapter = '') : null"
            >
              <v-card-title class="white__text">Chapitre 1</v-card-title>
            </div>
            <div
              class="circle white__circle"
              :style="activeChapter === 'black' ? '' : 'opacity: 0'"
              @click="activeChapter === 'black' ? (activeChapter = '') : null"
            >
              <v-card-title class="white__text">Chapitre 2</v-card-title>
            </div>
            <div
              class="circle white__circle"
              :style="activeChapter === 'red' ? '' : 'opacity: 0'"
              @click="activeChapter === 'red' ? (activeChapter = '') : null"
            >
              <v-card-title class="white__text">Chapitre 3</v-card-title>
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
              <v-card-title class="white__text">Chapitre 4</v-card-title>
            </div>
            <div
              class="circle white__circle"
              :style="activeChapter === 'green' ? '' : 'opacity: 0'"
              @click="activeChapter === 'green' ? (activeChapter = '') : null"
            >
              <v-card-title class="white__text">Chapitre 5</v-card-title>
            </div>
          </v-col>
        </v-col>
      </v-row>
    </transition>
    <v-row style="display: flex; justify-content: center; align-items: center">
      <v-card-title style="font-size: 2em; font-weight: bold"
        >PARIS 2024</v-card-title
      >
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
