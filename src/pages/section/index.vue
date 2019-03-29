<template>
  <div class="section-wrap">
    <div class="section-name">
      <img class="name-image" src="/static/images/user.png" background-size="cover" />
      <span class="text">Book Name</span>
    </div>

    <div class="section-content">
      <div class="content-title">
        <img class="catalog-icon" src="/static/images/user.png" background-size="cover" />
        <span class="text">书籍目录</span>
      </div>
      <div class="section-list">
        <div class="list-item" v-for="item in 5" :key="item">
          <div class="item-head">
            <img class="item-head__icon" src="/static/images/user.png" background-size="cover" />
          </div>
          <div class="item-body">
            <span class="body-text">第x章 名称xxxx</span>
          </div>
          <div class="item-foot">√</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data: function () {
    return {
    }
  },
  components: {},
  methods: {
  },
  onLoad () {
  }
}
</script>

<style scoped lang="scss">
.section-wrap {
  background: #F7F7F7;
}

.section-name {
  display: flex;
  align-items: center;
  background: #fff;
  padding: 0 50rpx;
  margin-bottom: 20rpx;

  .name-image {
    width: 120rpx;
    height: 120rpx;
    margin: 10rpx;
    border-radius: 50%;

  }
  .text {
    font-size: 16px;
    font-weight: bold;
  }
}


.section-content {
  background: #fff;

  .content-title {
    display: flex;
    align-items: center;
    margin-bottom: 10rpx;
    padding: 10rpx 30rpx;


    .catalog-icon {
      width: 60rpx;
      height: 60rpx;
      margin-right: 10rpx;
    }

    .text {
      font-size: 14px;
      color: #bbb;
    }
  }
}

.section-list {


  .item-head__icon {
    width: 60rpx;
    height: 60rpx;
    margin-right: 10rpx;
  }

  .list-item {
    display: flex;
    align-items: center;
    padding: 20rpx 30rpx;
    margin: 30rpx 50rpx;
    border-radius: 10rpx;
    box-shadow: 5rpx 10rpx 15rpx #eee;

    &:first-child {
      margin-top: 0;
    }

    .item-head {
      margin-right: 10rpx;

    }

    .item-body {
      flex: 1;
      font-size: 14px;
    }

    .item-foot {

    }
  }
}
</style>
