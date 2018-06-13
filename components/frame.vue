<template>
  <section class="frame" v-show="showFlag">
    <iframe id="frame" @click="getFrameEvent" src='/frame/'></iframe>
    <div ref="getIframe" @click="getIframe">获取iframe里面的方法</div>
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
      getIframe() {
        console.log(document.getElementById('frame').contentWindow)
      },
      getFrameEvent(event) {
        console.log(event)
      },
      show() {
        this.showFlag = true
      },
      hide() {
        this.showFlag = false
      }
    }
  }
</script>

<style>
  .frame {
    width: 100%;
    height: 600px;
  }

  .frame iframe {
    width: 100%;
    height: 100%;
    border: 0;
    padding: 0;
    margin: 0;
  }
</style>
