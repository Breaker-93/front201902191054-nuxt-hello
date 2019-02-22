<template>
  <section class="container">
    <div>
      <img class="rc-logo" src="~assets/img/rc-logo.jpg"/>
      <h2 class="title">
        This is news html!接收到的参数为：{{$route.query.id}}
      </h2>
      <ul>
        <li><a href="/">HOME</a></li>
        <li><nuxt-link to="/news/1">新闻1</nuxt-link></li>
        <li><nuxt-link :to="{name: 'news-id', params: {id: 2, title: '震惊！中国足球夺冠了！'}}">新闻2</nuxt-link></li>
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

<style scoped>
@keyframes heartBeat{
    0%{transform: scale(0.8,0.8); opacity: 1;}
    25%{transform: scale(1,1); opacity: 0.8;}
    100%{transform: scale(0.8,0.8); opacity: 1;}
}
.rc-logo {
  animation: heartBeat 1.5s infinite linear;
}
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
  font-size: 33px;
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
