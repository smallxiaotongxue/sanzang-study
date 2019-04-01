<template>
  <div class="index-page">

    <div class="index-function">
      <div class="function-list">
        <div class="list-item">
          <span class="function-icon iconfont icon-home-fill"></span>
          <span class="name">我的学习</span>
        </div>
        <div class="list-item">
          <span class="function-icon iconfont icon-solution"></span>
          <span class="name">班级排名</span>
        </div>
        <div class="list-item">
          <span class="function-icon iconfont icon-edit-fill"></span>
          <span class="name">面试题目</span>
        </div>
        <div class="list-item">
          <span class="function-icon iconfont icon-read"></span>
          <span class="name">热点资讯</span>
        </div>
      </div>
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
    <!--<form class="form-container">-->
      <!--<input type="text" class="form-control" :value="motto" placeholder="v-model" />-->
      <!--<input type="text" class="form-control" v-model="motto" placeholder="v-model" />-->
      <!--<input type="text" class="form-control" v-model.lazy="motto" placeholder="v-model.lazy" />-->
    <!--</form>-->

    <div class="function">
      <div class="function-item" @click="goToPage('/pages/ranking/main')">
        <div class="function-title">
          <img class="title-icon" src="/static/images/user.png" background-size="cover" />
          <span>班级排名</span>
        </div>
      </div>
      <div class="function-item" @click="goToPage('/pages/myStudy/main')">
        <div class="function-title">
          <img class="title-icon" src="/static/images/user.png" background-size="cover" />
          <span>我的学习</span>
        </div>
      </div>
    </div>

    <!-- 热门推荐文章 -->
    <div class="articles">
      <div class="articles-title">
        <!--<img alt="图标">-->
        <span>热门推荐</span>
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

.index-function {
  color: #fff;
  padding: 30rpx 40rpx;
  margin-bottom: 30rpx;
  background: linear-gradient(to bottom, lighten(#00A8E8, 20), #0e97ff);

  .function-list {
    display: flex;
    padding: 30rpx;
    font-size: 22rpx;

    .list-item {
      flex: 1;
      text-align: center;
    }
  }

  .function-icon {
    display: block;
    font-size: 50rpx;
    margin-bottom: 10rpx;
  }
}

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

  .name {
    font-size: 14px;
    padding: 10rpx;
  }
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

      .title-icon {
        width: 80rpx;
        height: 80rpx;
        margin: 10rpx;
        border-radius: 50%;
      }
    }
  }
}

.articles {
  margin: 20rpx 0;
  background: #f2f2f2;

  .articles-title {
    font-size: 14px;
    color: #0e97ff;
    margin: 10rpx 0;
    padding: 20rpx;
    background: #fff;
    /*box-shadow: 10rpx 10rpx 15rpx 0rpx #ddd;*/
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
