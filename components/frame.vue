<template>
  <section class="frame">
    <iframe id="frame" src='/frame/'></iframe>
    <div ref="getIframe" @click="getIframe">获取iframe里面的方法</div>
  </section>
</template>

<script>
  export default {
    methods: {
      getIframe() {
        console.log(document.getElementById('frame').contentWindow)
      }
    }
  }
</script>

<style>
</style>
