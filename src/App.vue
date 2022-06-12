<template>
  <div id="app">
    <header-component v-on:ganti-hero="gantiHero"></header-component>
    <main>
      <hero-component v-bind:heros="hero1"></hero-component>
      <hero-component v-bind:heros="hero2"></hero-component>
    </main>
    <footer-component></footer-component>
  </div>
</template>

<script>
import HeaderItem from "./components/Header-com.vue";
import FooterItem from "./components/Footer-com.vue";
import HeroItem from "./components/Hero-com.vue";
export default {
  components: {
    "header-component": HeaderItem,
    "footer-component": FooterItem,
    "hero-component": HeroItem,
  },
  name: "App",
  data: function () {
    return {
      hero1: {
        nama: "Aurora",
        type: "mage",
        gambar: "aurora.jpg",
      },
      hero2: {
        nama: "Zilong",
        type: "Fighter",
        gambar: "zilong.jpg",
      },
    };
  },
  methods: {
    gantiHero: function () {
      this.hero.nama = "Zilong";
      this.hero.type = "Fighter";
      this.hero.gambar = "zilong.jpg";
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
main img {
  width: 80px;
  border: 1px solid #ccc;
}
</style>
