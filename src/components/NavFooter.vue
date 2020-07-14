<template>
  <div class="footer">
    <div class="footer-logo">
      <img src="/imgs/logo-footer.png" alt="" />
      <p>小米商城</p>
    </div>
    <div class="footer-link">
      <a href="https://www.imooc.com/u/1343480" target="_blank">小张主页</a><span>|</span>
      <a href="https://coding.imooc.com/class/113.html" target="_blank">vue全栈课程</a><span>|</span>
      <a href="https://coding.imooc.com/class/236.html" target="_blank">react全家桶课程</a><span>|</span>
      <a href="https://coding.imooc.com/class/343.html" target="_blank">微信支付专项课程(H5+小程序+Node+Mongo)</a>
    </div>
    <div class="copyright">
      Copyright ©2019 <span class="domain">mi.futurefe.com</span> All Rights
      Reserved.
    </div>
  </div>
</template>

<script>
export default {
  nameL: 'nav-footer',
}
</script>

<style lang="scss" scoped>
@import './../assets/scss/config';

.footer {
  background-color: $colorB;
  font-size: $fontI;
  color: #999999;
  height: 234px;
  border-top: 4px solid $colorA;
  text-align: center;
  .footer-logo {
    margin-top: 46px;
    margin-bottom: 31px;
    img {
      width: 53px;
      height: 36px;
      margin-bottom: 13px;
    }
  }
  .footer-link {
    margin-bottom: 13px;
    a {
      color: #999999;
      display: inline-block;
    }
    span {
      padding: 0 10px;
    }
  }
  .copyright {
    .domain {
      color: $colorA;
    }
  }
}
</style>
