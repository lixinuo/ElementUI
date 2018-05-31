<template>
  <div>
    <div class="top">
      <span class="demonstration">默认</span>
      <el-date-picker v-model="value1" type="datetime" placeholder="选择日期时间"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">带快捷选项</span>
      <el-date-picker v-model="value2" type="datetime" placeholder="选择日期时间" :picker-options="pickerOptions1"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">设置默认时间</span>
      <el-date-picker v-model="value3" type="datetime" placeholder="选择日期时间" default-time="12:00:00"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">日期和时间范围（默认）</span>
      <el-date-picker v-model="value4" type="datetimerange" range-separator="至" start-placeholder="开始日期" end-placeholder="结束日期"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">日期和时间范围（快捷选项）</span>
      <el-date-picker v-model="value5" type="datetimerange" range-separator="至" start-placeholder="开始日期" end-placeholder="结束日期" :picker-options="pickerOptions2" align="right"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">默认的起始和结束时刻 起始时刻为 12:00:00</span>
      <el-date-picker v-model="value6" type="datetimerange" start-placeholder="开始日期" end-placeholder="结束日期" :default-time="['12:00:00']"></el-date-picker>
    </div>

    <div class="top">
      <span class="demonstration">起始时刻为12:00:00 结束时刻为08:00:00</span>
      <el-date-picker v-model="value7" type="datetimerange" align="right" start-placeholder="开始日期" end-placeholder="结束日期" :default-time="['12:00:00', '08:00:00']"></el-date-picker>
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
      value12: [],
      pickerOptions1: {
        shortcuts:[{
          text: '今天',
          onClick(picker) {
            picker.$emit('pick', new Date());
          }
        },{
          text: '昨天',
          onClick(picker) {
            const date = new Date();
            date.setTime(date.getTime() - 3600 * 1000 * 24);
            picker.$emit('pick', date)
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
            const start = new Date();
            const end = new Date();
            start.setTime(start.getTime() - 3600 * 1000 * 24 * 7);
            picker.$emit('pick', [start, end]);
          }
        },{
          text: '最近一个月',
          onClick(picker) {
            const start = new Date();
            const end = new Date();
            start.setTime(start.getTime() - 3600 * 1000 * 24 * 30);
            picker.$emit('pick', [start, end]);
          }
        },{
          text: '最近三个月',
          onClick(picker) {
            const start = new Date();
            const end = new Date();
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
