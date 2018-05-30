<template>
  <div>
    <div class="top">
      <span class="demonstration">默认</span>
      <el-date-picker v-model="value1" type="date" placeholder="选择日期"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">带快捷选项</span>
      <el-date-picker v-model="value2" align="right" type="date" placeholder="选择日期" :picker-options="pickerOptions1"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">周</span>
      <el-date-picker v-model="value3" type="week" format="yyyy第WW周" placeholder="选择周"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">月</span>
      <el-date-picker v-model="value4" type="month" placeholder="选择月"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">年</span>
      <el-date-picker v-model="value5" type="year" placeholder="选择年"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">多个日期</span>
      <el-date-picker v-model="value6" type="dates" placeholder="选择一个或多个日期"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">选择日期范围（默认）</span>
      <el-date-picker v-model="value7" type="daterange" range-separator="至" start-placeholder="开始日期" end-placeholder="结束日期"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">选择日期范围（带快捷选项）</span>
      <el-date-picker v-model="value8" type="daterange" align="right" unlink-panels range-separator="至" start-placeholder="开始日期" end-placeholder="结束日期" :picker-options="pickerOptions2">
      </el-date-picker>
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
      value4: '',
      value5: '',
      value6: [],
      value7: '',
      value8: '',
      pickerOptions1: {
        disabledDate(time) {
          return time.getTime() > Date.now();
        },
        shortcuts: [{
          text: '今天',
          onClick(picker) {
            picker.$emit('pick', new Date());
          }
        },{
          text: '昨天',
          onClick(picker) {
            const date = new Date();
            date.setTime(date.getTime() - 3600 * 1000 * 24);
            picker.$emit('pick', date);
          }
        },{
          text: '一周前',
          onClick(picker) {
            const date = new Date();
            date.setTime(date.getTime() - 3600 * 1000 * 24 * 7);
            picker.$emit('pick', date);
          }
        }]
      },
      pickerOptions2: {
        shortcuts: [{
          text: '最近一周',
          onClick(picker) {
            const end = new Date();
            const start = new Date();
            start.setTime(start.getTime() - 3600 * 1000 * 24 * 7);
            picker.$emit('pick', [start, end])
          }
        },{
          text: '最近一个月',
          onClick(picker) {
            const end = new Date();
            const start = new Date();
            start.setTime(start.getTime() - 3600 * 1000 * 24 * 30);
            picker.$emit('pick', [start, end]);
          }
        },{
          text: '最近三个月',
          onClick(picker) {
            const end = new Date();
            const start = new Date();
            start.setTime(start.getTime() - 3600 * 1000 * 24 * 90);
            picker.$emit('pick', [start, end]);
          }
        }]
      }
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
