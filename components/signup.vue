<template lang="html">
  <section class="signup" v-show="showFlag">
    <div class="close" @click="hide">
      关闭
    </div>
    <iframe id='iframeli' class="contentWrap" src='https://modesens.com/accounts/signup/?next='></iframe>
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

<style lang="css">
.signup {
  width: 600px;
  height: 680px;
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}
.signup .close {
  position: absolute;
  right: 15px;
  top: 15px;
  cursor: pointer;
  font-size: 12px;
}
.signup iframe {
  width: 100%;
  height: 100%;
}
</style>
