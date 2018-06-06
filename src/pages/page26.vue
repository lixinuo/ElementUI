<template>
  <div>
    <div class="top">
      <span class="demonstration">有默认值</span>
      <el-color-picker v-model="color1"></el-color-picker>
    </div>

    <div class="top">
      <span class="demonstration">无默认值</span>
      <el-color-picker v-model="color2"></el-color-picker>
    </div>

    <div class="top">
      <span class="demonstration">选择透明度</span>
      <el-color-picker v-model="color3" show-alpha></el-color-picker>
    </div>

    <div class="top">
      <span class="demonstration">预定义颜色</span>
      <el-color-picker v-model="color4" show-alpha :predefine="predefineColors"></el-color-picker>
    </div>

    <div class="top">
      <span class="demonstration"></span>
    </div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      color1: '#409EFF',
      color2: null,
      color3: 'rgba(19, 206, 102, 0.8)',
      color4: 'rgna(255, 69, 0, 0.68)',
      color5: null,
      predefineColors: ['#ff4500', '#ff8c00' , '#ffd700', 'rgba(255,69,0,0.68)']
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
