<template>
  <a v-if="isExternalLink" target="_blank" :href="link.to">{{ link.name }}</a>
  <router-link
    v-else
    :to="{ name: link.to, params: { id: link.id } }"
    v-slot="{ isActive }"
  >
    <a :class="isActive ? 'is-active' : 'normal-link'">
      {{ link.name }}
    </a>
  </router-link>
</template>

<script>
export default {
  props: {
    link: {
      type: Object,
      requiered: true,
    },
  },
  computed: {
    isExternalLink() {
      return this.link.to.startsWith("http");
    },
  },
};
</script>

<style scope>
.is-active {
  color: #42b983;
}
.normal-link {
  color: #2c3e50;
}
</style>