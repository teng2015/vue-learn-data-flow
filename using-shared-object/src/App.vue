<template>
  <div id="app">
    <header>
      <h2>使用共享对象同步数据</h2>
      <p><a href="https://github.com/Lin07ux/notes/blob/master/Web/Vue/Vue%20Vuex%20%E4%B8%AD%E6%95%B0%E6%8D%AE%E6%B5%81%E7%AE%80%E4%BB%8B.md">查看相关介绍</a></p>
    </header>

    <div class="row">
      <div class="col">
        <client clientid="Clent A"></client>
      </div>
      <div class="col">
        <client clientid="Clent B"></client>
      </div>
    </div>
  </div>
</template>

<script>
import Client from './components/client.vue'

export default {
  name: 'App',
  components: {
    client: Client
  }
}
</script>

<style>
* {padding: 0; margin: 0; box-sizing: border-box;}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
a {color: #42b983; text-decoration: none;}
.row {display: flex; justify-content: space-around;}
.col {flex: 1; padding: 20px 40px;}
</style>
