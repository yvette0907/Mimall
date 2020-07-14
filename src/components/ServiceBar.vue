<template>
  <div class="service">
    <div class="container">
      <ul>
        <li><span class="icon-setting"></span>预约维修服务</li>
        <li><span class="icon-7day"></span>7天无理由退货</li>
        <li><span class="icon-15day"></span>15天免费换货</li>
        <li><span class="icon-post"></span>满150包邮</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  nameL: 'service-bar',
}
</script>

<style lang="scss">
@import './../assets/scss/base';
@import './../assets/scss/mixin';

.service {
  padding: 33px 0;
  color: #666;
  font-size: 16px;
  text-align: center;
  li {
      display: inline-block;
    //   四块，每块应该是25%，但是我们不会直接设置成这个宽度，会小一点点，因为不同的浏览器可能不同
      width: 24.9%;
      text-align: center;
      border-right: 1px solid #e5e5e5;
      span{
        display:inline-block;
        width:20px;
        height:20px;
        vertical-align: middle;
        margin-right:8px;
      }
      .icon-setting {
         @include bgImg(20px, 20px, '/imgs/icon-setting.png')
      }
      .icon-7day {
         @include bgImg(20px, 20px, '/imgs/icon-7day.png')
      }
      .icon-15day {
         @include bgImg(20px, 20px, '/imgs/icon-15day.png')
      }
      .icon-post {
         @include bgImg(20px, 20px, '/imgs/icon-post.png')
      }
  }
}
</style>
