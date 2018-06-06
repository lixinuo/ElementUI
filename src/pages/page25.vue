<template>
  <div>
    <div class="top">
      <span class="demonstration">默认不区分颜色</span>
      <el-rate v-model="value1"></el-rate>
    </div>

    <div class="top">
      <span class="demonstration">区分颜色</span>
      <el-rate v-model="value2" :colors="['#99A9BF', '#F7BA2A', '#FF9900']"></el-rate>
    </div>

    <div class="top">
      <span class="demonstration">辅助文字</span>
      <el-rate v-model="value3" show-text></el-rate>
    </div>

    <div class="top">
      <span class="demonstration">其它icon</span>
      <el-rate v-model="value4" :icon-classes="['icon-rate-face-1', 'icon-rate-face-2', 'icon-rate-face-3']" void-icon-class="icon-rate-face-off" :colors="['#99A9BF', '#F7BA2A', '#FF9900']"></el-rate>
    </div>

    <div class="top">
      <span class="demonstration">只读</span>
      <el-rate v-model="value5" disabled show-score text-color="ff9900" color-template="{value}"></el-rate>
    </div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      value1: null,
      value2: null,
      value3: null,
      value4: null,
      value5: 3.7
    }
  },
  methods: {

  },
  mounted() {
  }
}
</script>
<style>
.top { padding: 15px 25px; }
.top .demonstration { font-size: 14px; color: #8492a6; padding: 0 30px; }
.top .el-slider { float: right; width: 70%; margin-right: 20px; }
.upload-demo { width: 360px; }
</style>
