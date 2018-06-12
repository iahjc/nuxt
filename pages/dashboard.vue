<template>
  <section class="container">
    <header>
      <ul>
        <li>服装</li>
        <li>箱包</li>
        <li>鞋履</li>
        <li>配饰</li>
        <li>美妆</li>
        <li><router-link to="/modesens">modesens vue</router-link></li>
        <li>dashboard</li>
      </ul>

      <div class="user">
        <span>登录</span>&nbsp;|&nbsp;<span>注册</span>
      </div>
    </header>

    <div class="dashboard">
      dashboard
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      showFlag: false
    }
  },
  methods: {
  }
}
</script>

<style>
.dashboard {
  width: 100%;
  text-align: center;
  margin-top: 300px;
}

.container header {
  width: 1200px;
  display: flex;
  justify-content: space-between;
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
