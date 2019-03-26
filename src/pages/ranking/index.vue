<template>
  <div>
    <div class="ranking-header">
      <div class="header-left">
        <p class="title">唐三藏</p>
        <p class="subhead">青铜五 第三名</p>
      </div>
      <div class="header-right">
        <div class="class-ranking">3 / 40</div>
      </div>
    </div>
    <div class="ranking-container">
      <ul class="rank-list">
        <li class="list-item" v-for="(item, index) in number" :key="index">
          <div class="item-header">
            <span class="index">{{item + 1}}</span>
          </div>
          <div class="item-body">
            <img class="head-img" src="/static/images/user.png"/>
            <div class="name">唐三藏</div>
            <div class="level">青铜五</div>
          </div>
          <!--<div class="item-foot"></div>-->
        </li>
      </ul>
    </div>
  </div>
</template>

<script>

export default {
  components: {},

  data () {
    return {
      number: 10
    }
  },

  created () {
  }
}
</script>

<style scoped lang="scss">

.ranking-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 30rpx 0;
  margin: 0 30rpx;
  border-bottom: 1rpx solid #e7e7e7;

  .header-left {
    display: flex;
    flex-direction: column;

    .title {
      font-size: 14px;
      margin: 10rpx 0;
    }

    .subhead {
      font-size: 12px;
      color: #a4a4a4;
    }
  }

  .header-right {
    display: flex;
    font-size: 14px;
    align-items: center;

    .class-ranking {
      color: #4EC1FF;
      background: aliceblue;
      padding: 10rpx 30rpx;
      border-radius: 60rpx;
    }
  }
}

.ranking-container {
  margin: 30rpx;
}

.rank-list {
  .head-img {
    display: inline-block;
    width: 60rpx;
    height: 60rpx;
    margin: 5rpx 10rpx;
    border-radius: 50%;
  }

  .list-item {
    display: flex;
    align-items: center;
    min-height: 90rpx;
    font-size: 14px;

    .item-header {
      width: 50rpx;
      text-align: center;
    }

    .item-body {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex: 1;

      .name {
        flex: 1;
        margin: 0 10rpx;
      }

      .level {
        margin: 0 10rpx;
      }
    }
  }
}

</style>
