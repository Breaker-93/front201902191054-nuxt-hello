<template>
  <section class="container">
    <div>
      hello
      <logo/>
      <h1 class="title">
        front201902191054-nuxt-hello
      </h1>
      <h2 class="subtitle">
        My outstanding Nuxt.js project
      </h2>
      <ul>
        <li><a href="/">HOME</a></li>
        <li><a href="/about">ABOUT(a)</a></li>
        <!-- <nuxt-link to="/about">ABOUT(nuxt-link)</nuxt-link> -->
        <li><nuxt-link :to="{name: 'about', params: {id: '3399'}}">ABOUT(nuxt-link)</nuxt-link></li>
        <li><nuxt-link :to="{name: 'news', query: {id: '3366'}}">NEWS</nuxt-link></li>
      </ul>

    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
