<template>
  <div class="header">
    <h1>{{ font }}</h1>
    <div :title="titles" v-for="item in img">
      <img :src="item.url" alt="titles">
    </div>
  </div>
</template>

<script>
  export default {
    name: "Header",
    data() {
      return {
        titles: 'hi everybody',
        font: '我是马尔扎哈',
        img: []
      }
    },
    methods: {
      postData() {
        this.$http({
          method: 'post',
          url: 'http://testjx.etlpx.com/app/index/advert',
        }).then((res) => {
          this.img = res['data']['data']
        })
      }
    },
    mounted() {
      this.postData()
    },
  }

</script>

<style scoped>
  .header {
    background: indianred;
    height: 300px;
    width: 100%;
  }
</style>
