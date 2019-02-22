<template>
  <section class="container">
    <div>
      <img class="rc-logo" src="~assets/img/rc-logo.jpg"/>
      <h1>
        Detail html!接收到的参数为：{{$route.params.id}}
      </h1>
      <h2>
         title:{{$route.params.title}}
      </h2>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  transition: "test",
  components: {
    Logo
  },
  validate ({ params }) {
    // Must be a number
    return /^\d+$/.test(params.id)
  },
  //独立设置head信息
  head(){
    return{
      title:this.$route.params.title,
      meta:[
        {hid: 'hid-' + Math.random() * 100000,name:'description',content:'This is news page'},
        {hid: 'hid-' + Math.random() * 100000,name:'keywords',content:'中国足球,夺冠'}
      ]
    }
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
  /* font-size: 100px; */
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
