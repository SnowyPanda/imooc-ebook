<template>
  <transition name="slide-down">
      <div class="title-wrapper" v-show="ifTitleAndMenuShow">
        <div class="left">
          <span class="icon-back iconfont icon"></span>
        </div>
        <div class="right">
          <div class="icon-wrapper">
            <span class="icon-cart iconfont icon"></span>
          </div>
          <div class="icon-wrapper">
            <span class="icon-person iconfont icon"></span>
          </div>
          <div class="icon-wrapper">
            <span class="icon-more iconfont icon"></span>
          </div>
        </div>
      </div>
    </transition>
</template>

<script>
export default {
  props: {
    ifTitleAndMenuShow: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang='scss' scoped>
@import 'styles/global.scss';
.title-wrapper {
      position: absolute;
      display: flex;
      top: 0;
      left: 0;
      width: 100%;
      height: px2rem(48);
      z-index: 101;
      background-color: white;
      box-shadow: 0 0 px2rem(8) px2rem(8) rgba(0,0,0,0.15);
    .left {
      flex: 0 0 px2rem(60);
      @include center;
    }
    .right {
      flex: 1;
      display: flex;
      justify-content: flex-end;
      .icon-wrapper{
        flex: 0 0 px2rem(40);
        @include center;
      }
    }
  }
</style>
