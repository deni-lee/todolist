<template>
  <div id="app">
    <div id="nav">
      <router-link to="/all">全部</router-link> |
      <router-link to="/active">未完成</router-link> |
      <router-link to="/complete">已完成</router-link>
    </div>
    <TodoInput></TodoInput>
    <TodoListItem v-for="index in todoIndex" :key="index" :index="index" />
    
  </div>
</template>

<script>
import TodoInput from '@/components/TodoInput/Index.vue'
import TodoListItem from '@/components/TodoListItem/index.vue'


export default {
  components:{
    TodoInput,
    TodoListItem
  },
  computed:{
    todoIndex() {
      return this.$store.getters['todoIndex']
    }
  },
  // mounted() {
  //   this.$store.dispatch('INIT_TODOS')
  // }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
