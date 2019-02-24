<template>
  <section class="container">
    <div>
      <img class="rc-logo" src="~assets/img/rc-logo.jpg"/>>
      <h1 class="title">
        This is about html!接收到的参数为：{{$route.params.id}}
      </h1>
      <h1>姓名：{{info.name}}</h1>
      <h2>年龄：{{info.age}}</h2>
      <h2>兴趣：{{info.interest}}</h2>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'
import axios from 'axios'
export default {
  components: {
    Logo
  },
  async asyncData () {
    let {data} = await axios.get('https://api.myjson.com/bins/1a6ffa')
    return {info: data}
  }
}
</script>

<style>
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
