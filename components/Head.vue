<template>
  <header class="header">
    <ul>
      <li><a href="/product/women/clothing/">服装</a></li>
      <li><a href="/product/women/bags/">箱包</a></li>
      <li><a href="/product/women/shoes/">鞋履</a></li>
      <li><a href="/product/women/accessories/">配饰</a></li>
      <li><a href="/product/women/beauty/">美妆</a></li>
      <li><router-link to="/modesens">modesens vue</router-link></li>
      <li><router-link to="/dashboard">dashboard</router-link></li>
    </ul>

    <div class="user">
      <span @click="login">登录</span>&nbsp;|&nbsp;<span @click="signup">注册</span>
    </div>

    <Login ref="login"></Login>
    <Signup ref="signup"></Signup>
  </header>
</template>

<script>
import Login from '~/components/login.vue'
import Signup from '~/components/signup.vue'

  export default {
    components: {
      Login,
      Signup
    },
    methods: {
      login() {
        this.$refs.login.show()
      },
      signup() {
        this.$refs.signup.show()
      }
    }
  }
</script>

<style>
.header {
  width: 1200px;
  display: flex;
  justify-content: space-between;
  color: #000;
  margin: 0 auto;
}

.header .user {
  font-size: 12px;
  line-height: 45px;
}

.header .user span {
  cursor: pointer;
}

.header ul {
  display: flex;
  height: 45px;

}

.header ul li {
  list-style: none;
  height: 45px;
  line-height: 45px;
  width: 120px;
  text-align: center;
  font-size: 12px;
}
.header ul li a {
  color: #000;
}
</style>
