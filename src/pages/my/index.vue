<template>
  <div class="my">
    <div class="my-info">
      <img @click="toLogin" :src="avator" alt="">
      <div class="info__text" @click="toLogin">
        <p>{{userInfo.nickName}}</p>
        <p v-if="!userInfo.nickname">点击登录</p>
        <p v-else>微信用户</p>
      </div>
    </div>

    <ul class="my-list">
      <li class="list-item">
        <div>推荐给朋友</div>
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  onShow () {},
  created () {},
  mounted () {},
  data () {
    return {
      avator: 'http://yanxuan.nosdn.127.net/8945ae63d940cc42406c3f67019c5cb6.png',
      allcheck: false,
      Listids: [],
      userInfo: {}
    }
  },
  components: {},
  methods: {
    toLogin () {}
  },
  computed: {}
}
</script>

<style scoped lang="scss">

.my {
  background: #f3f3f3;
  padding-bottom: 1rpx;

  .my-info {
    width: 100%;
    height: 250rpx;
    display: flex;
    align-items: center;
    background: #333;
    padding: 0 30rpx;
    box-sizing: border-box;

    .info__text {
      margin-left: 30rpx;
      p {
        color: #fff;
        font-size: 16px;
        margin-bottom: 10rpx
      }
      p:nth-child(2) {
        font-size: 14px;
      }
    }
  }

  img {
    height: 120rpx;
    width: 120rpx;
    border-radius: 50%
  }

  .my-list {
    margin: 20rpx 0;

    .list-item {
      display: flex;
      align-items: center;
      background: #fff;
      font-size: 14px;
      min-height: 100rpx;
      padding: 0 30rpx;

      .item-body {

      }
    }

  }
}
</style>
