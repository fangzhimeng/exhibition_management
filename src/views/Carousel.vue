<template>
  <el-carousel :interval="interval" arrow="always" indicator-position="outside" @change="handleChange">
    <el-carousel-item v-for="(item, index) in items" :key="index">
      <img :src="item.image" alt="">
      <div class="carousel-item-text">
        <h3>{{ item.title }}</h3>
        <p>{{ item.description }}</p>
      </div>
    </el-carousel-item>
  </el-carousel>
</template>

<script>
export default {
  name: 'Carousel',
  props: {
    items: {
      type: Array,
      required: true
    },
    interval: {
      type: Number,
      default: 5000
    }
  },
  methods: {
    handleChange(index) {
      console.log(`轮播图切换到第 ${index + 1} 张`)
    }
  }
}
</script>
