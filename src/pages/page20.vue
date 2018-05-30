<template>
  <div>
    <div class="top">
      <span class="demonstration">默认</span>
      <el-slider v-model="value1"></el-slider>
    </div>

    <div class="top">
      <span class="demonstration">自定义初始值</span>
      <el-slider v-model="value2"></el-slider>
    </div>

    <div class="top">
      <span class="demonstration">隐藏Tooptip</span>
      <el-slider v-model="value3" :show-tooltip="false"></el-slider>
    </div>

    <div class="top">
      <span class="demonstration">格式化Tooptip</span>
      <el-slider v-model="value4" :format-tooltip="formatTooltip"></el-slider>
    </div>

    <div class="top">
      <span class="demonstration">禁用</span>
      <el-slider v-model="value5" disabled></el-slider>
    </div>

    <div class="top">
      <span class="demonstration">不显示间断点</span>
      <el-slider v-model="value6" :step="10"></el-slider>
    </div>

    <div class="top">
      <span class="demonstration">显示间断点</span>
      <el-slider v-model="value7" :step="10" show-stops></el-slider>
    </div>

    <div class="top">
      <span class="demonstration">带输入框</span>
      <el-slider v-model="value8" show-input></el-slider>
    </div>

    <div class="top">
      <span class="demonstration">范围选择</span>
      <el-slider v-model="value9" range show-stops :max="10"></el-slider>
    </div>

    <div class="top">
      <span class="demonstration">竖向模式</span>
      <el-slider v-model="value10" vertical height="200px"></el-slider>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      value1: 0,
      value2: 50,
      value3: 36,
      value4: 48,
      value5: 20,
      value6: 0,
      value7: 0,
      value8: 0,
      value9: [4, 8],
      value10: 0
    }
  },
  methods: {
    formatTooltip(val) {
      return val/100;
    }
  },
  mounted() {
  }
}
</script>
<style>
.top { padding: 15px 25px; }
.top .demonstration { font-size: 14px; color: #8492a6; }
.top .el-slider { float: right; width: 70%; margin-right: 20px; }
</style>
