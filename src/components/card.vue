<template>
  <div>
    <p class="card">
      {{text}}
    </p>
  </div>
</template>

<script>
export default {
  name: 'card',

  props: ['text']
}
</script>

<style>
.card {
  padding: 10rpx;
  font-size: 14px;
}
</style>
