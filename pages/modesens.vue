<template>
  <section class="container">
    <header>
      <ul>
        <li>服装</li>
        <li>箱包</li>
        <li>鞋履</li>
        <li>配饰</li>
        <li>美妆</li>
        <li>modesens vue</li>
        <li><router-link to="/dashboard">dashboard</router-link></li>
      </ul>

      <div class="user">
        <span>登录</span>&nbsp;|&nbsp;<span>注册</span>
      </div>
    </header>

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
import axios from 'axios'
export default {
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
