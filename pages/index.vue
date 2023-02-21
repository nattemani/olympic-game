<template>
  <div>
    <v-row class="banner light-bg d-flex align-center justify-center">
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
        class="banner2 grey-bg d-flex align-center justify-center"
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
            <div class="circle blue__circle" @click="activeChapter = 'blue'">
              <v-card-title class="blue__text">Chapitre 1</v-card-title>
            </div>
            <div class="circle black__circle" @click="activeChapter = 'black'">
              <v-card-title class="black__text">Chapitre 2</v-card-title>
            </div>
            <div class="circle red__circle" @click="activeChapter = 'red'">
              <v-card-title class="red__text">Chapitre 3</v-card-title>
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
              @click="activeChapter = 'yellow'"
            >
              <v-card-title class="yellow__text">Chapitre 4</v-card-title>
            </div>
            <div class="circle green__circle" @click="activeChapter = 'green'">
              <v-card-title class="green__text">Chapitre 5</v-card-title>
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
      activeChapter: ''
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
  align-items: center;
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

.grey-bg {
  background-color: lightgray;
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
  background-color: black;
}
.black__bg {
  background-color: black;
}
.black__circle:hover {
  background: white;
  border: solid 5px black;
}
.black__text {
  color: black;
}

.yellow__circle {
  background-color: #f4b33d;
}
.yellow__bg {
  background-color: #f4b33d;
}
.yellow__circle:hover {
  background: white;
  border: solid 5px #f4b33d;
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
  border: solid 5px #0083c8;
}

.blue__text {
  color: #0083c8;
}

.white__circle {
  border: solid 5px white;
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
  border: solid 5px #e9354e;
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
  border: solid 5px #00a851;
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
