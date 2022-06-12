<template>
  <div id="app">
    <header-component></header-component>
    <main>
      <ul>
        <li>
          <img :src="gambar" alt="" />
          <p>{{ hero.nama }}</p>
          <p>
            Jenis Hero : <em>{{ hero.type }}</em>
          </p>
        </li>
      </ul>
    </main>
    <footer-component></footer-component>
  </div>
</template>

<script>
import HeaderItem from "./components/Header-com.vue";
import FooterItem from "./components/Footer-com.vue";
export default {
  components: {
    "header-component": HeaderItem,
    "footer-component": FooterItem,
  },
  name: "App",
  data: function () {
    return {
      hero: {
        nama: "Aurora",
        type: "mage",
        gambar: "aurora.jpg",
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
  computed: {
    gambar: function () {
      return require("./assets/hero/" + this.hero.gambar);
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
