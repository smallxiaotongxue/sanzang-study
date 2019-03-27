<template>
  <div class="book-bg">
    <ul class="book-list">
      <li class="list-item" v-for="(item, index) in 5" :key="index">
        <div class="item-head">
          <div class="head-left">
            <img class="language-icon" src="/static/images/user.png" background-size="cover" alt="icon">
            <span class="language-name">Java</span>
          </div>
          <span class="head-right">更多 ></span>
        </div>
        <div class="item-body">
          <swiper next-margin="100rpx" style="height: 310rpx">
            <swiper-item  v-for="(cardItem, index1) in 5" :key="index1">
              <book-card></book-card>
            </swiper-item>
          </swiper>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import bookCard from '@/components/book-card'

export default {
  props: {
    bookList: {
      type: Array,
      default: []
    }
  },
  components: {
    bookCard
  }
}
</script>

<style scoped lang="scss">
.book-bg {
  background: aliceblue;
  padding-bottom: 20rpx ;
}

.book-list {

  .list-item {
    padding: 15rpx 0 0;

    &:first-child {
      margin-top: 0;
    }

    .item-head {
      display: flex;
      justify-content: space-between;
      align-items: center;
      min-height: 60rpx;
      padding: 0 20rpx;
      margin-bottom: 10rpx;

      .head-left {
        display: flex;
        align-items: center;
      }

      .language-icon {
        width: 50rpx;
        height: 50rpx;
        margin: 5rpx;
        border-radius: 50%;
      }

      .language-name {
        font-size: 12px;
        margin: 0 5rpx;
      }

      .head-right {
        color: #0e97ff;
        font-size: 12px;
      }
    }

    .item-body {

    }

  }
}
</style>
