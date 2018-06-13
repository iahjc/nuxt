<template>
  <section class="container">
    <Head/>
    <div class="dashboard">
      dashboard
    </div>
  </section>
</template>

<script>
import Head from '~/components/Head.vue'

export default {
  components: {
    Head
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
