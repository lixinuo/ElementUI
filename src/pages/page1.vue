<template>
  <div>
    <div class="top">
      <span class="demonstration">默认</span>
      <el-upload
    </div>

    <div class="top">
      <span class="demonstration">带快捷选项</span>
    </div>

    <div class="top">
      <span class="demonstration">设置默认时间</span>
    </div>

    <div class="top">
      <span class="demonstration">日期和时间范围（默认）</span>
    </div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      value1: '',
      value2: '',
      value3: '',
      value4: [],
      value5: [],
      value6: '',
      value7: '',
      value8: '',
      value9: '',
      value10: '',
      value11: '',
      value12: []
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
</style>
