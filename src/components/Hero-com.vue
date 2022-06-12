<template>
  <ul>
    <li>
      <img :src="gambar" alt="" />
      <p>{{ index + 1 }}--{{ heros.nama }}</p>
      <p>
        Jenis Hero : <em>{{ heros.type }}</em>
      </p>
    </li>
  </ul>
</template>
<script>
export default {
  props: ["heros", "index"],
  computed: {
    gambar: function () {
      return require("../assets/hero/" + this.heros.gambar);
    },
  },
};
</script>
<style scoped>
p {
  color: salmon;
}

li {
  list-style: none;
}
</style>
