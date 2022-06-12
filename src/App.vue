<template>
  <div id="app">
    <header-component v-on:ganti-hero="gantiHero"></header-component>
    <main>
      <p>Hero-hero terbaik minggu ini</p>
      <article v-if="!selectedHero">
        <div v-for="(item, index) in hero" :key="item.id">
          <hero-component v-bind:heros="item" :index="index"></hero-component>
        </div>
      </article>
      <article v-else>
        <hero-component v-bind:heros="selectedHero" :index="0"></hero-component>
      </article>
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
      hero: [
        {
          id: 1,
          nama: "Akai",
          type: "Tank",
          gambar: "akai.jpg",
        },
        {
          id: 2,
          nama: "Zilong",
          type: "Fighter",
          gambar: "zilong.jpg",
        },
        { id: 3, nama: "Aurora", type: "Mage", gambar: "aurora.jpg" },
        {
          id: 4,
          nama: "Bruno",
          type: "Marksman",
          gambar: "bruno.jpg",
        },
      ],
      selectedHero: "",
    };
  },
  methods: {
    gantiHero: function () {
      this.selectedHero = this.randomHero();
    },
    randomHero: function () {
      return this.hero[Math.floor(Math.random() * this.hero.length)];
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

article {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

main {
  text-align: center;
}
</style>
