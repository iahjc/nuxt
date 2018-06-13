<template>
  <section class="frame">
    <iframe id="frame" @click="getFrameEvent" src='/frame/'></iframe>
    <div ref="getIframe" @click="getIframe">获取iframe里面的方法</div>
  </section>
</template>

<script>
  export default {
    methods: {
      getIframe() {
        console.log(document.getElementById('frame').contentWindow)
      },
      getFrameEvent(event) {
        console.log(event)
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
