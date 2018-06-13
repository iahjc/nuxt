<template>
  <section class="login" v-show="showFlag">
    <div class="close" @click="hide">
      关闭
    </div>
    <iframe class="contentWrap" src='/accounts/login/?next=/dashboard'></iframe>
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
  .login {
    width: 600px;
    height: 680px;
    position: fixed;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
  .login .close {
    position: absolute;
    right: 15px;
    top: 15px;
    cursor: pointer;
    font-size: 12px;
  }
  .login iframe {
    width: 100%;
    height: 100%;
  }
</style>
