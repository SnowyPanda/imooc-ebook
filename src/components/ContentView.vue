<template>
  <transition name="slide-right">
    <div class="content">
        <div class="content-wrapper" v-if="bookAvailable">
            <div class="content-item" v-for="(item,index) in navigation.toc" :key="index" @click="jumpTo(item.href)">
              <span class="text">{{item.label}}</span>
            </div>
        </div>
        <div class="text-wrapper" v-else>
          加载中...
        </div>
    </div>
  </transition>
</template>

<script>
export default {
  props: {
    ifShowContent: Boolean,
    navigation: Array,
    bookAvailable: Boolean
  },
  methods: {
    jumpTo (link) {
      this.$emit('jumpTo', link)
    }
  }
}
console.log(this.navigation)
</script>

<style lang='scss' scoped>
@import 'styles/global.scss';
.content{
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 80%;
  background: white;
  z-index: 102;
  .content-wrapper{
     width: 100%;
     height: 100%;
     overflow: auto;
    .content-item{
      width: 100%;
      padding: px2rem(20) px2rem(15);
      border-bottom: px2rem(1) solid #f4f4f4;
      .text{
      font-size: px2rem(22);
      text-align: left;
            color: #000;
      }
    }
  }
}
</style>
