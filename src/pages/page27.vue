<template>
  <div>
    <div class="top">
      <span class="demonstration">Transfer穿梭框</span>
      <el-transfer v-model="value1" :data="data"></el-transfer>
    </div>

    <div class="top">
      <span class="demonstration">可搜索</span>
      <el-transfer v-model="value2" :data="data2" filterable :filter-method="filterMethod" filter-placeholder="请输入城市拼音"></el-transfer>
    </div>

    <div class="top">
      <span class="demonstration">可自定义</span>
    </div>

    <div class="top">
      <span class="demonstration">预定义颜色</span>
    </div>

    <div class="top">
      <span class="demonstration"></span>
    </div>

  </div>
</template>

<script>
export default {
  data () {
    const generateData = _ => {
      const data = [];
      for(let i = 1; i <= 15; i++){
        data.push({
          key: i,
          label: `备选项${ i }`,
          disabled: i % 4 === 0
        });
      }
      return data;
    };
    const generateData2 = _ => {
      const data = [];
      const cities = ['上海', '北京', '广州', '深圳', '南京', '西安', '成都'];
      const pinyin = ['shanghai', 'beijing', 'guangzhou', 'shenzhen', 'nanjing', 'xian', 'chengdu'];
      cities.forEach((city, index) => {
        data.push({
          label: city,
          key: index,
          pinyin: pinyin[index]
        });
      });
      return data;
    }
    return {
      data: generateData(),
      value1: [1, 4],
      data2: generateData2(),
      value2: [],
      filterMethod(query, item) {
        return item.pinyin.indexOf(query) > -1;
      }

    };

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
