<template>
  <div class="hello">
    <input type="text" v-model="msg">
    <h1>{{ msg }}</h1>
    <Nav></Nav>
    <Header :parentValue="msg"></Header>
  </div>
</template>

<script>
import Header from './header.vue'

export default {
  name: 'HelloWorld',
  components: { Header },
  data () {
    return {
      msg: 'hello world'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
