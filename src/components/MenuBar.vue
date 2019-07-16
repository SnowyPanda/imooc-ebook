<template>
      <div class="menu-bar">
        <transition name="slide-up">
            <div class="menu-wrapper" v-show="ifTitleAndMenuShow">
                <div class="icon-wrapper">
                <span class="icon-menu iconfont icon"></span>
                </div>
                <div class="icon-wrapper">
                <span class="icon-progress iconfont icon"></span>
                </div>
                <div class="icon-wrapper">
                <span class="icon-bright iconfont icon"></span>
                </div>
                <div class="icon-wrapper">
                <span class="icon-a iconfont icon" @click="showSetting">A</span>
                </div>
            </div>
        </transition>
        <transition name="slide-up">
            <div class="setting-wrapper" v-show="ifSettingShow">
                <div class="setting-font-size"></div>
            </div>
        </transition>
      </div>
</template>

<script>
export default {
  props: {
    ifTitleAndMenuShow: {
      type: Boolean,
      default: false
    }
  },
  data () {
    return {
      ifSettingShow: false
    }
  },
  methods: {
    showSetting () {
      this.ifSettingShow = true
    },
    hideSetting () {
      this.ifSettingShow = false
    }
  }
}
</script>

<style lang='scss' scoped>
@import 'styles/global.scss';
.menu-bar {
    .menu-wrapper{
        position: absolute;
        bottom: 0;
        left: 0;
        z-index: 101;
        display: flex;
        height: px2rem(48);
        width: 100%;
        background-color: white;
        box-shadow: 0 px2rem(-8) px2rem(8) rgba(0,0,0,0.15);
        .icon-wrapper{
            flex: 1;
            @include center;
            .icon-progress{
                font-size: px2rem(28);
            }
            .icon-bright{
                font-size: px2rem(28);
            }
            .icon-menu{
                font-size: px2rem(28);
            }
        }
    }
    .setting-wrapper{
        position: absolute;
        bottom: px2rem(48);
        left: 0;
        width: 100%;
        height: 60px;
        background-color: white;
        box-shadow: 0 px2rem(-8) px2rem(8) rgba(0,0,0,0.15);
        .setting-font-size{

        }
    }
}
</style>
