<template>
  <header class="navbar is-fixed-top is-transparent">
    <div class="navbar-brand">
      <a class="navbar-item" href="/"><logo /></a>
      <div class="navbar-burger burger"  onclick="document.querySelector('.navbar-menu').classList.toggle('is-active'); document.querySelector('.navbar-burger').classList.toggle('is-active'); document.querySelector('.navbar').classList.toggle('is-light');">
        <span></span>
        <span></span>
        <span></span>
      </div>
    </div>
    <div role="navigation" class="navbar-menu">
      <div class="navbar-end">
          <div class="navbar-item" v-if="!/\/.*?\/.*/.test(route.path)" v-for="route in this.$router.options.routes">
            <nuxt-link :to="{ name: route.name }">{{ route.name.charAt(0).toUpperCase() + route.name.slice(1) }}</nuxt-link>
          </div>
      </div>
    </div>
  </header>
</template>

<script>
  import Logo from '~/components/Logo.vue'
  export default {
    components: {
      Logo
    }
  }
</script>
