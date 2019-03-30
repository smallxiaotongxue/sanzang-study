<template>
  <div>
    <div class="question-bg"></div>
    <div class="question">
      <div class="answer-progress">
        <div class="progress-wrap">
          <div class="progress-position">
            <i-progress
              :hide-info="true"
              stroke-width="10"
              :percent="answerPrecent"
              :status="precentStatus"
            ></i-progress>
          </div>
        </div>
        <div class="progress-tips">
          <div class="num">4</div>
          <div class="text">待完成</div>
        </div>
      </div>
      <div class="question-content">
        <swiper style="height:calc(100vh - 120rpx)" :current="current">
          <swiper-item>
            <scroll-view scroll-y="true" style="height: 100%">
              <div class="question-name">
                <div class="text">CSS的Scoped私有作用域和深度选择器???</div>
              </div>
              <div class="answer-options">
                <ul class="options-list">
                  <li class="list-item">
                    <div class="option-btn">xxxxxxxxxx</div>
                  </li>
                  <li class="list-item">
                    <div class="option-btn">xxxxxxxxxx</div>
                  </li>
                  <li class="list-item">
                    <div class="option-btn">xxxxxxxxxx</div>
                  </li>
                  <li class="list-item">
                    <div class="option-btn">xxxxxxxxxx</div>
                  </li>
                </ul>
              </div>
            </scroll-view>
          </swiper-item>
        </swiper>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data: function () {
    return {
      currentNum: 6,
      allNum: 10
    }
  },
  computed: {
    answerPrecent () {
      return this.currentNum / this.allNum * 100 || ''
    },
    precentStatus () {
      return this.readPrecent === 100 ? 'success' : 'active'
    }
  },
  components: {},
  methods: {},
  onLoad () {
  }
}
</script>

<style lang="scss" scoped>

.question-bg {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1000;
  background: linear-gradient(to bottom, #1EB1F7, #9be2ff)
}

.question {

  .answer-progress {
    display: flex;
    align-items: center;
    min-height: 80rpx;
    padding: 20rpx;

    .progress-wrap {
      flex: 1;
      height: 40rpx;
      padding: 0 10rpx;
      border-radius: 50rpx;
      background: #fff;

      .progress-position {
        margin-top: -6px;
      }
    }

    .progress-tips {
      width: 150rpx;
      margin-left: 10rpx;
      color: #fff;
      text-align: center;

      .num {
        font-size: 16px;
        font-weight: bold;
      }

      .text {
        font-size: 12px;
      }
    }
  }

  .question-content {

    .question-name {
      min-height: 350rpx;
      color: #fff;
      font-size: 18px;
      font-weight: bold;
      padding: 10rpx 30rpx;
      display: flex;
      align-items: center;
      justify-content: center;

      .text {
        word-break: break-all;
      }
    }

    .answer-options {

      .options-list {
        padding: 30rpx;

        .list-item {
          margin: 50rpx;
        }
      }
    }

    .option-btn {
      padding: 10rpx 20rpx;
      min-height: 70rpx;
      line-height: 70rpx;
      font-size: 14px;
      text-align: center;
      transition: all .3s linear;
      color: #fff;
      border: 1px solid #fff;
      border-radius: 50rpx;

      &:active {
        background: #9be2ff;
      }
    }
  }
}
</style>
