<template>
  <div>
    <div class="top">
      <span class="demonstration">固定时间点</span>
      <el-time-select v-model="value1" :picker-options="{start: '08:30', step: '00:15', end: '18:30'}" placeholder="选择时间"></el-time-select>
    </div>

    <div class="top">
      <span class="demonstration">任意时间点</span>
      <el-time-picker v-model="value2" :picker-options="{selectableRange: '18:30:00 - 20:30:00'}" placeholder="任意时间点"></el-time-picker>
      <el-time-picker v-model="value3" arrow-control :picker-options="{selectableRange: '18:30:00 - 10:30:00'}" placeholder="任意时间点"></el-time-picker>
    </div>

    <div class="top">
      <span class="demonstration">固定时间范围</span>
      <el-time-select v-model="startTime" :picker-options="{start: '08:30', step: '00:15', end: '18:30'}" placeholder="起始时间"></el-time-select>
      <el-time-select v-model="endTime" :picker-options="{start: '08:30', step: '00:15', end: '18:30', minTime: startTime}" placeholder="结束时间"></el-time-select>
    </div>

    <div class="top">
      <span class="demonstration">任意时间范围</span>
      <el-time-picker is-range v-model="value4" range-separator="至" start-placeholder="开始时间" end-placeholder="结束时间" placeholder="选择时间范围"></el-time-picker>
      <el-time-picker is-range arrow-control v-model="value5" range-separator="至" start-placeholder="开始时间" end-placeholder="结束时间" placeholder="选择时间范围"></el-time-picker>
    </div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      value1: 0,
      value2: new Date(2016, 9, 10, 18, 40),
      value3: new Date(2016, 9, 10, 18, 40),
      startTime: '',
      endTime: '',
      value4: [new Date(2016, 9, 10, 8, 40), new Date(2016, 9, 10, 9, 40)],
      value5: [new Date(2016, 9, 10, 8, 40), new Date(2016, 9, 10, 9, 40)]
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
.top .demonstration { font-size: 14px; color: #8492a6; padding: 0 30px; }
.top .el-slider { float: right; width: 70%; margin-right: 20px; }
</style>
