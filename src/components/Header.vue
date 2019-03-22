<template>
  <div>
    <Nav></Nav>
    <div class="header">
      <h1>{{ font }}</h1>

        <img v-for="(item, index) in img" v-text="index" :class="{odd :index % 2}" :src="item.url" alt="titles">

      <div>
        <ol>
          <li>
            <h3>响应式，双向绑定，js改变展现改变，展现改变，js改变</h3>
            <div>
              <ul>
                <li>v-model</li>
                <li>v-html</li>
                <li>v-text</li>
                <li>v-for</li>
                <li>v-on</li>
                <li>v-if/v-show</li>
                <li>v-bind</li>
              </ul>
            </div>
          </li>
          <li>
            <h3>组件</h3>
            <div>
              <ul>
                <li>header</li>
                <li>login</li>
                <li>pagenation</li>
                <li>footer</li>
                <li>slidashow</li>
              </ul>
            </div>
          </li>
          <li></li>
        </ol>
      </div>
    </div>
    <div class="nav"></div>
  </div>

</template>


<script>
  import Nav from './nav'

  export default {
    name: "Header",
    data() {
      return {
        titles: 'hi everybody',
        font: '我是axios接口请求',
        img: []
      }
    },
    components: {Nav},
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
    props: ['parentValue'],
    mounted() {
      this.postData()
      this.font = 'xxxxx';
    },
    created() {

    }
  }

</script>

<style scoped>
  .header {
    background: indianred;
    height: 300px;
  }

  .nav {
    background: goldenrod;
    height: 300px;
  }
</style>
