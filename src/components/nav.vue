<template>
  <div>
    <div class="nav" v-bind:class="navClass" v-on:click="changBg" v-html="name"></div>
    <div v-text="name"></div>
  </div>
</template>

<script>
    export default {
        name: "nav",
        data: function () {
          return{
            navClass: 'red-bg',
            name: '<span>nav</span>'
          }
        },
      methods: {
        changBg(){
          this.navClass = 'yellow-bg'
        }
      }
    }
</script>

<style scoped>
.nav{
  width: 100px;
  height: 100px;
  font-size: 30px;
  font-weight: 700;
}
  .red-bg{
    background-color: red;
  }
  .yellow-bg{
    background-color: yellow;
  }
</style>
