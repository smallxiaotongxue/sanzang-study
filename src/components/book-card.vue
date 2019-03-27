<template>
  <div class="card">
    <div class="card-wrap">
      <div class="card-intro">
        <div class="intro-left">
          <img class="intro-cover__img" src="/static/images/icon-1.png"  alt="icon">
        </div>
        <div class="intro-right">
          <h4 class="book-name">Java轻松学</h4>
          <p class="book-section">共10章</p>
          <p class="total-number">有10人正在阅读</p>
        </div>
      </div>
      <div class="card-options">
        <div class="options-left">
          <div class="more">
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>
          </div>
        </div>
        <div class="options-right">
          <a class="btn btn-primary circle" style="min-width: 100rpx">去闯关</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {}
}
</script>

<style scoped lang="scss">

.card {
  display: flex;
  align-items: center;
  justify-content: center;

  .card-wrap {
    display: flex;
    width: 100%;
    flex-direction: column;
    margin: 10rpx 20rpx;
    border-radius: 20rpx;
    background: #fff;
    box-shadow: 0 0 20rpx #ddd;
  }


  .card-intro {
    display: flex;
    align-items: center;
    padding: 30rpx 30rpx 10rpx;

    .intro-left {
      margin-right: 30rpx;

      .intro-cover__img {
        width: 120rpx;
        height: 150rpx;
        border-radius: 10rpx;
      }
    }

    .intro-right {
      flex: 1;

      .book-name {
        font-size: 14px;
        font-weight: bold;
        margin-bottom: 40rpx;
      }

      .book-section, .total-number {
        color: #c2c2c2;
        font-size: 12px;
        line-height: 16px;
      }
    }
  }

  .card-options {
    display: flex;
    align-items: center;

    .options-left {
      flex: 1;
      padding: 0 20rpx;

      .more {
        margin-left: 20rpx;
        display: flex;
        align-items: center;

        .dot {
          width: 10rpx;
          height: 10rpx;
          background: #ddd;
          border-radius: 50%;
          margin-left: 8rpx;
        }
      }
    }

    .options-right {
      margin-right: 10rpx;
    }
  }

  .btn {
    margin: 20rpx;
    padding: 10rpx 20rpx;
    font-size: 14px;
    text-align: center;
    transition: all .3s linear;

    &.btn-primary {
      background: #0e97ff;
      color: #fff;

      &:active {
        background: darken(#0e97ff, 10%);
      }
    }

    &.circle {
      border-radius: 50rpx;
    }
  }
}

</style>
