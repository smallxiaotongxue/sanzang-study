<template>
  <div>

    <swiper
      :indicator-dots="true"
      :autoplay="true"
      :circular="true"
      interval="5000"
      duration="1000"
    >
      <swiper-item v-for="(item, index) in imgUrls" :key="index">
        <img :src="item" style="width: 100vw; height: 300rpx;"/>
      </swiper-item>
    </swiper>

    <div class="userinfo" @click="bindViewTap">
      <img class="userinfo-avatar" src="/static/images/user.png" background-size="cover" />

      <div class="userinfo-nickname">
        <div>
          <card :text="userInfo.nickName"></card>
          <card :text="userInfo.class"></card>
        </div>
      </div>

      <img class="userinfo-level" :src="userInfo.level" background-size="cover" />
    </div>
    <!--<form class="form-container">-->
      <!--<input type="text" class="form-control" :value="motto" placeholder="v-model" />-->
      <!--<input type="text" class="form-control" v-model="motto" placeholder="v-model" />-->
      <!--<input type="text" class="form-control" v-model.lazy="motto" placeholder="v-model.lazy" />-->
    <!--</form>-->

    <div class="function">
      <div class="function-item" @click="goToPage('/pages/ranking/main')">
        <div class="function-title">
          <img class="userinfo-avatar" src="/static/images/user.png" background-size="cover" />
          <span>班级排名</span>
        </div>
      </div>
      <div class="function-item" @click="goToPage('/pages/counter/main')">
        <div class="function-title">
          <img class="userinfo-avatar" src="/static/images/user.png" background-size="cover" />
          <span>段位查询</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import card from '@/components/card'

export default {
  data () {
    return {
      motto: 'Hello miniprograme',
      userInfo: {
        nickName: '唐三藏',
        class: '计算机一班',
        level: 'http://mpvue.com/assets/logo.png'
      },
      imgUrls: [
        'https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640',
        'https://images.unsplash.com/photo-1551214012-84f95e060dee?w=640',
        'https://images.unsplash.com/photo-1551446591-142875a901a1?w=640'
      ]
    }
  },

  components: {
    card
  },

  methods: {
    bindViewTap () {
      const url = '../logs/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    goToPage (url) {
      mpvue.navigateTo({ url })
    }
  },

  created () {
    // let app = getApp()
  }
}
</script>

<style scoped lang="scss">
.userinfo {
  display: flex;
  background: aliceblue;
  margin: 20rpx 0;
  /*box-shadow: 5rpx 5rpx 15rpx 5rpx #ddd;*/
}

.userinfo-avatar, .userinfo-level {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  display: flex;
  flex: 1;
  align-items: center;
  color: #aaa;
}

.function {
  display: flex;
  margin: 20rpx 0;

  .function-item {
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20rpx;
    font-size: 14px;
    min-height: 70rpx;
    background: antiquewhite;
    margin-right: 6rpx;
    transition: all .3s linear;

    &:active {
      background: #e2d3bf;
    }

    &:nth-child(2n) {
      margin-right: 0;
    }

    .function-title {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }
  }
}

</style>
