<template>
  <div class="index">
    <div class="container">
      <!-- 轮播组件 -->
      <div class="swiper-box">
        <div class="nav-menu">
          <ul class="menu-wrap">
            <li class="menu-item">
              <a href="javascript:;">手机 电话卡</a>
              <div class="children">
                <ul v-for="(item, index) in menuList" :key="index">
                  <li v-for="(sub, num) in item" :key="num">
                    <a :href="sub ? '/#/product/' + sub.id : ''">
                      <img
                        :src="sub ? sub.img : '/imgs/item-box-1.png'"
                        alt=""
                      />
                      {{ sub ? sub.name : '小米9' }}
                    </a>
                  </li>
                </ul>
              </div>
            </li>
            <li class="menu-item">
              <a href="javascript:;">电视 盒子</a>
            </li>
            <li class="menu-item">
              <a href="javascript:;">笔记本 平板</a>
            </li>
            <li class="menu-item">
              <a href="javascript:;">家电 插线板</a>
            </li>
            <li class="menu-item">
              <a href="javascript:;">出行 穿戴</a>
            </li>
            <li class="menu-item">
              <a href="javascript:;">智能 路由器</a>
            </li>
            <li class="menu-item">
              <a href="javascript:;">电源 配件</a>
            </li>
            <li class="menu-item">
              <a href="javascript:;">生活 箱包</a>
            </li>
          </ul>
        </div>
        <!-- 调用swiper轮播组件来使用 -->
        <swiper :options="swiperOption">
          <swiper-slide v-for="(item, index) in slideList" :key="index">
            <a :href="'/#/product/' + item.id">
              <img :src="item.img" />
            </a>
          </swiper-slide>
          <!-- optional controls -->
          <div class="swiper-pagination" slot="pagination"></div>
          <div class="swiper-button-prev" slot="button-prev"></div>
          <div class="swiper-button-next" slot="button-next"></div>
        </swiper>
      </div>
      <div class="ads-box">
        <a
          :href="'/#/product/' + item.id"
          v-for="(item, index) in adsList"
          :key="index"
        >
          <img :src="item.img" />
        </a>
      </div>
      <div class="banner">
        <a href="'/#/product/' + 30">
          <img src="/imgs/banner-1.png" />
        </a>
      </div>
    </div>
    <div class="product-box">
      <div class="container">
        <h2>手机</h2>
        <div class="wrapper">
          <div class="banner-left">
            <a href="'/#/product/' + 35">
              <img src="/imgs/mix-alpha.jpg" alt="" />
            </a>
          </div>
          <div class="list-box">
            <div class="list" v-for="(item, index) in phoneList" :key="index">
              <div class="item" v-for="(i, j) in item" :key="j">
                <span>新品</span>
                <div class="item-img">
                  <img src="/imgs/item-box-1.png" alt="" />
                </div>
                <div class="item-info">
                  <h3>小米9</h3>
                  <p>骁龙855，索尼4800万超广角微距</p>
                  <p class="price">2999元</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <service-bar></service-bar>
  </div>
</template>
<script>
import ServiceBar from './../components/ServiceBar'
import { swiper, swiperSlide } from 'vue-awesome-swiper'
import 'swiper/dist/css/swiper.css'
export default {
  name: 'index',
  data() {
    return {
      swiperOption: {
        autoplay: true,
        loop: true,
        effect: 'cube',
        cubeEffect: {
          slideShadows: true,
          shadow: true,
          shadowOffset: 100,
          shadowScale: 0.6,
        },
        pagination: {
          el: '.swiper-pagination',
          clickable: true,
        },
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
      },
      slideList: [
        {
          id: '42',
          img: '/imgs/slider/slide-1.jpg',
        },
        {
          id: '45',
          img: '/imgs/slider/slide-2.jpg',
        },
        {
          id: '46',
          img: '/imgs/slider/slide-3.jpg',
        },
        {
          id: '',
          img: '/imgs/slider/slide-4.jpg',
        },
        {
          id: '',
          img: '/imgs/slider/slide-5.jpg',
        },
      ],
      menuList: [
        [
          {
            id: 30,
            img: '/imgs/item-box-1.png',
            name: '小米CC9',
          },
          {
            id: 31,
            img: '/imgs/item-box-2.png',
            name: '小米8青春版',
          },
          {
            id: 32,
            img: '/imgs/item-box-3.jpg',
            name: 'Redmi K20 Pro',
          },
          {
            id: 33,
            img: '/imgs/item-box-4.jpg',
            name: '移动4G专区',
          },
        ],
        [0, 0, 0, 0],
        [0, 0, 0, 0],
        [0, 0, 0, 0],
        [0, 0, 0, 0],
        [0, 0, 0, 0],
      ],
      adsList: [
        {
          id: 33,
          img: '/imgs/item-box-1.png',
        },
        {
          id: 48,
          img: '/imgs/item-box-2.png',
        },
        {
          id: 45,
          img: '/imgs/item-box-3.jpg',
        },
        {
          id: 47,
          img: '/imgs/item-box-4.jpg',
        },
      ],
      phoneList: [
        [1, 1, 1, 1],
        [1, 1, 1, 1],
      ],
    }
  },
  components: {
    ServiceBar,
    swiper,
    swiperSlide,
  },
}
</script>

<style lang="scss" scoped>
@import './../assets/scss/mixin';
.index {
  .swiper-box {
    .swiper-container {
      height: 451px;
      .swiper-button-prev {
        left: 274px;
      }
      img {
        height: 100%;
        width: 100%;
      }
    }
    .nav-menu {
      box-sizing: border-box;
      position: absolute;
      left: 0;
      right: 0;
      width: 264px;
      height: 451px;
      z-index: 9;
      padding: 26px 0;
      background-color: #55585a7a;
      .menu-wrap {
        .menu-item {
          height: 50px;
          line-height: 50px;
          a {
            position: relative;
            display: block;
            font-size: 16px;
            color: #ffffff;
            padding-left: 30px;
            &:after {
              content: '';
              @include bgImg(10px, 15px, '/imgs/icon-arrow.png');
              position: absolute;
              right: 30px;
              top: 17.5px;
            }
          }
          &:hover {
            background-color: #ff6600;
            .children {
              display: block;
            }
          }
          .children {
            display: none;
            width: 962px;
            height: 451px;
            background-color: #ffffff;
            position: absolute;
            left: 264px;
            top: 0;
            border: 1px solid #e5e5e5;
            ul {
              display: flex;
              justify-content: space-between; //两边对齐
              height: 75px;
              li {
                height: 75px;
                line-height: 75px;
                //  width: 241px;
                flex: 1; //均分每一份，和上面设置宽度为241是一样的效果
                padding-left: 23px;
                a {
                  color: #333333;
                  font-size: 14px;
                  img {
                    width: 35px;
                    height: 42px;
                    vertical-align: middle; //让图片和文字是居中的
                    margin-right: 15px;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  .ads-box {
    @include flex();
    margin-top: 14px;
    margin-bottom: 31px;
    a {
      width: 286px;
      height: 167px;
    }
  }
  .banner {
    margin-bottom: 50px;
  }
  .product-box {
    background-color: #f5f5f5;
    padding: 30px 0 50px;
    h2 {
      font-size: 22px;
      height: 21px;
      line-height: 21px;
      color: #333333;
      margin-bottom: 20px;
    }
    .wrapper {
      display: flex;
      .banner-left {
        margin-right: 16px;
        img {
          width: 224px;
          height: 619px;
        }
      }
      .list-box {
        .list {
          @include flex();
          width: 986px;
          // height: 302px;
          margin-bottom: 14px;
          &:last-child {
            margin-bottom: 0;
          }
          .item {
            width: 236px;
            height: 302px;
            background-color: #fff;
            text-align: center;
            span {
            }
            .item-img {
              img {
                height: 195px;
              }
            }
            .item-info {
              h3 {
                font-size: 14px;
                color: #333333;
                line-height: 14px;
                font-weight: bold;
              }
              p {
                color: #999999;
                line-height: 13px;
                margin: 6px auto 13px;
              }
              .price {
                color: #f20000;
                font-size: 14px;
                font-weight: bold;
                cursor: pointer;
                &:after {
                  @include bgImg(22px, 22px, '/imgs/icon-cart-hover.png');
                  content: '';
                  margin-left: 5px;
                  vertical-align: middle;
                }
              }
            }
          }
        }
      }
    }
  }
}
</style>
