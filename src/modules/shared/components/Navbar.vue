<template>
  <div>
    <!--     <router-link :to="{ name: 'pokemon-home' }">Pokemon List</router-link>
    <router-link :to="{ name: 'pokemon-id', params: { id: 85 } }"
      >Pokemon por id</router-link
    >
    <router-link :to="{ name: 'pokemon-about' }">Pokemon About</router-link> -->

    <CustomLink v-for="link in links" :key="link.to" :link="link" />
  </div>
</template>
<script>
import { defineAsyncComponent } from "vue";
export default {
  components: {
    CustomLink: defineAsyncComponent(() => import("./CustomLink.vue")),
  },
  data() {
    return {
      links: [
        { to: "/home", name: "Pokemons" },
        { to: "/pokemondid/151", name: "Pokemons por id" },
        { to: "/about", name: "Pokemons About" },
        { to: "https://www.google.es/", name: "Google" },
      ],
    };
  },
};
</script>

<style scoped>
div {
  padding: 0 30px;
}

div a {
  font-weight: bold;
  color: #2c3e50;
  margin: 0 10px;
}
/* a.router-link-exact-active {
  color: #42b983;
} */
</style>
