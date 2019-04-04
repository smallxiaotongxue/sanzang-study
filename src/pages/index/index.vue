<template>
  <div class="index-page">

    <div class="index-function">
      <div class="function-list">
        <div class="list-item">
          <span class="function-icon iconfont icon-home-fill" @click="goToPage('/pages/myStudy/main')"></span>
          <span class="name">我的学习</span>
        </div>
        <div class="list-item" @click="goToPage('/pages/ranking/main')">
          <span class="function-icon iconfont icon-solution"></span>
          <span class="name">班级排名</span>
        </div>
        <div class="list-item" @click="goToPage('/pages/interview/main')">
          <span class="function-icon iconfont icon-edit-fill"></span>
          <span class="name">面试题目</span>
        </div>
        <div class="list-item" @click="goToPage('/pages/interview/main')">
          <span class="function-icon iconfont icon-read"></span>
          <span class="name">热点资讯</span>
        </div>
      </div>

      <div class="tips">
        <div class="tips-head">TOP</div>
        <div class="tips-swiper">
          <swiper class="swiper_container" vertical="true" autoplay="true" circular="true" interval="3000">
            <swiper-item v-for="item in inforList" :key="item">
              <div class="swiper_item">{{item.title}}</div>
            </swiper-item>
          </swiper>
        </div>
      </div>

    </div>

    <div class="userinfo" @click="bindViewTap">
      <img class="userinfo-avatar" src="/static/images/user.png" background-size="cover" />

      <div class="userinfo-nickname">
        <div>
          <div class="name">{{userInfo.nickName}}</div>
          <div class="name">{{userInfo.class}}</div>
        </div>
      </div>

      <img class="userinfo-level" :src="userInfo.level" background-size="cover" />
    </div>

    <swiper
      :indicator-dots="true"
      :autoplay="true"
      :circular="true"
      interval="5000"
      duration="1000"
    >
      <swiper-item v-for="(item, index) in imgUrls" :key="index">
        <img :src="item" style="width: 100vw; height: 100%;"/>
      </swiper-item>
    </swiper>

    <!-- 热门推荐文章 -->
    <div class="articles">
      <div class="articles-title">
        <!--<img alt="图标">-->
        <span class="title-name">热门推荐</span>
      </div>
      <div class="articles-contents">
        <ul class="articles-list">
          <li class="list-item" v-for="(item, index) in 5" :key="index">
            <div class="item-head">
              <div class="head-left">
                <img class="upload-icon" src="/static/images/user.png" background-size="cover" alt="icon">
                <span class="upload-name">CopPan</span>
              </div>
              <span class="upload-module-name">Java</span>
            </div>
            <div class="item-body">
              <div class="news-title">Java 8新的时间日期库的20个使用示例</div>
              <div class="news-intro">有人问我学习一个新库的最佳途径是什么？我的回答是，就是在实际项目中那样去使用它。在一个真实的项目中会有各种各样的需求，这会促使开发人员去探索和研究这个新库。简言之，只有任务本身才会真正促使你去探索及学习。java 8的新的日期及时间API也是一样。</div>
            </div>
            <div class="item-foot">
              <div class="news-comment">喜欢</div>
              <div class="news-comment">评论</div>
            </div>
          </li>
        </ul>
      </div>
    </div>

  </div>
</template>

<script>

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
      ],
      inforList: [
        { url: 'url', title: '微信小程序swiper实现轮播图，可触发点击事件' },
        { url: 'url', title: '小程序js实现【滚动文字广播、动态滚动公告栏】动画效果' },
        { url: 'url', title: '纳尼，要回去毕业答辩了？' }
      ]
    }
  },

  components: {},

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

.index-page {
  background: #f2f2f2;
}

.index-function {
  color: #fff;
  padding: 30rpx 40rpx;
  margin-bottom: 20rpx;
  background: linear-gradient(to bottom, lighten(#00A8E8, 20), #0e97ff);

  .function-list {
    display: flex;
    padding: 30rpx 30rpx 0;
    font-size: 22rpx;

    .list-item {
      flex: 1;
      text-align: center;
    }
  }

  .function-icon {
    display: block;
    font-size: 60rpx;
    margin-bottom: 10rpx;
  }

  .tips {
    position: relative;
    bottom: -40rpx;
    display: flex;
    align-items: center;
    background-color: #fff;
    border-radius: 10rpx;
    font-size: 24rpx;
    box-shadow: 0 5rpx 15rpx #ddd;

    .tips-head {
      color: #0e97ff;
      font-weight: bold;
      padding: 0 20rpx;
      border-right: 1rpx solid #c2c2c2;
    }

    .tips-swiper {
      flex: 1;
      padding: 0 20rpx;
    }

    .swiper_container {
      color: #000;
      width: 100%;
      height: 60rpx;
      background-color: #fff;

      .swiper_item {
        width: 100%;
        height: 60rpx;
        line-height: 60rpx;
        font-size: 22rpx;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
        letter-spacing: 2px;
      }
    }
  }
}

.userinfo {
  display: flex;
  background: aliceblue;
  margin: 25rpx 0 20rpx;
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

  .name {
    font-size: 14px;
    padding: 10rpx;
  }
}

.articles {
  margin: 20rpx 0;
  background: #f2f2f2;

  .articles-title {
    margin: 10rpx 0;
    padding: 20rpx;
    background: #fff;
    /*box-shadow: 10rpx 10rpx 15rpx 0rpx #ddd;*/

    .title-name {
      font-size: 14px;
      font-weight: bold;
      color: #0e97ff;
      padding: 0 20rpx;
      border-left: 8rpx solid #0e97ff;
    }
  }

  .articles-contents {
    margin-top: 10rpx;
  }

}

.articles-list {

  .list-item {
    background: #fff;
    padding: 15rpx 0;
    margin: 10rpx 0;
    transition: all .3s linear;

    &:active {
      background: #a6e0ff;
    }

    .item-head {
      display: flex;
      justify-content: space-between;
      align-items: center;
      min-height: 80rpx;
      padding: 0 20rpx;

      .head-left {
        display: flex;
        align-items: center;
      }

      .upload-icon {
        width: 50rpx;
        height: 50rpx;
        margin: 5rpx;
        border-radius: 50%;
      }

      .upload-name {
        font-size: 12px;
        margin: 0 5rpx;
      }

      .upload-module-name {
        color: #c2c2c2;
        font-size: 12px;
        margin: 0 20rpx;
      }
    }

    .item-body {
      padding: 0 20rpx;

      .news-title {
        font-size: 16px;
        font-weight: bold;
      }

      .news-intro {
        color: #c2c2c2;
        font-size: 12px;
        line-height: 16px;
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        word-break: break-all;
        -webkit-box-orient: vertical;
        -webkit-line-clamp: 2;
      }
    }

    .item-foot {
      padding: 0 20rpx;
      margin-top: 10rpx;

      .news-comment {
        color: #c2c2c2;
        font-size: 12px;
        vertical-align: center;
        display: inline-block;
        margin-right: 20rpx;

        &:before {
          content: '';
          display: inline-block;
          width: 16rpx;
          height: 16rpx;
          background: #c2c2c2;
          margin-right: 10rpx;
        }
      }
    }
  }
}

</style>
