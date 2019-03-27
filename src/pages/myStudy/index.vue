<template>
  <div>
    <div class="my-tab">
      <i-tabs :current="current" @change="handleChange">
        <i-tab v-for="(item, index) in TAB_NAME_LIST" :key="item.key" :title="item.title"></i-tab>
      </i-tabs>

      <swiper class="tab-content" style="height:calc(100vh - 84rpx)" :current="current" @change="tabChange">
        <!-- 推荐书籍 -->
        <swiper-item>
          <scroll-view scroll-y="true" style="height: 100%">
            <recommend-list></recommend-list>
          </scroll-view>
        </swiper-item>

        <!-- 未完成 -->
        <swiper-item>
          <scroll-view scroll-y="true" style="height: 100%">
            <div class="reading-list">
              <div class="list-item" v-for="(item, index) in 5" :key="index">
                <book-card></book-card>
              </div>
            </div>
          </scroll-view>
        </swiper-item>

        <!-- 已完成 -->
        <swiper-item>
          <scroll-view scroll-y="true" style="height: 100%">
            <div class="no-result">
              <!--<img src="" alt="">-->
              <div class="title">
                <p>Oh，No木有已通关的书!</p>
                <p>加油闯关看书吧！</p>
              </div>
            </div>
          </scroll-view>
        </swiper-item>
      </swiper>

    </div>
  </div>
</template>

<script>
import recommendList from '@/components/recommend-list'
import bookCard from '@/components/book-card'

export default {
  data: function () {
    return {
      current: '0',
      TAB_NAME_LIST: [
        {
          key: '0',
          title: '推荐书籍'
        },
        {
          key: '1',
          title: '未通关'
        },
        {
          key: '2',
          title: '已通关'
        }
      ]
    }
  },
  components: {
    recommendList,
    bookCard
  },
  methods: {
    handleChange ({ target }) {
      this.current = target.key
    },
    tabChange ({ target }) {
      this.current = target.current
    }
  },
  onLoad () {
  }
}
</script>

<style scoped lang="scss">

.reading-list {
  padding: 20rpx;
  .list-item {
    margin-bottom: 20rpx;
  }
}

.no-result {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;

  .title {
    text-align: center;
    color: #ccc;

    p:nth-child(1) {
      font-size: 16px;
      font-weight: bold;
      margin-bottom: 10rpx;
    }

    p:nth-child(2) {
      font-size: 14px;
    }
  }
}

</style>
