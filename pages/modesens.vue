<template>
  <section class="container">
    <Head>

    </Head>

    <ul class="getApi">
      <li @click="getNavJson">获得导航数据 (get)</li>
      <li v-show="m_a.length > 0">
        {{m_a}}
      </li>
    </ul>

    <div class="modesens">
      modesens vue
    </div>
  </section>
</template>

<script>
import Head from '~/components/Head.vue'
import axios from 'axios'
export default {
  components: {
    Head
  },
  data() {
    return {
      navJson: null,
      m_a: []
    }
  },
  methods: {
    getNavJson() {
      this.getNavHeaderJson().then((res) => {
        console.log(res.navHeadJson)
        this.navJson = res.navHeadJson
        this.m_a = this.navJson.m_a
        console.log(this.m_a)
      })
    },
    getNavHeaderJson() {
      let url = `https://modesens.com/getnavhead/?csrfmiddlewaretoken=i5cwyQxw5c8qgkJ6JvvOQ2Qgjp1EZeokrmztDeiHZxdJxZqNMlFXCFnOsD2cM1Xd&fromweb=1`
      return axios.get(url, {}).then((res) => {
        return Promise.resolve(res.data)
      })
    }
  }
}
</script>

<style>
.getApi {
  width: 1200px;
  margin: 30px auto;
  font-size: 12px;
  cursor: pointer;
}
.modesens {
  width: 100%;
  text-align: center;
  margin-top: 150px;
}

.container header {
  width: 1200px;
  display: flex;
  justify-content: space-between;
  margin: 0 auto;
}

.container header .user {
  font-size: 12px;
  line-height: 45px;
}

.container header ul {
  display: flex;
  height: 45px;

}

.container header ul li {
  list-style: none;
  height: 45px;
  line-height: 45px;
  width: 120px;
  text-align: center;
  font-size: 12px;
}
</style>
