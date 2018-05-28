<template>
  <div>
    <div>
      <el-select v-model="value" placeholder="请选择">
        <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value"></el-option>
      </el-select>
    </div>

    <div style="margin-top: 20px;">
      <el-select v-model="value2" placeholder="请选择">
        <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value" :disabled="item.disabled"></el-option>
      </el-select>
    </div>

    <div style="margin-top: 20px;">
      <el-select v-model="value3" disabled placeholder="请选择">
        <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value"></el-option>
      </el-select>
    </div>

    <div style="margin-top: 20px;">
      <el-select v-model="value4" clearable placeholder="请选择">
        <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value"></el-option>
      </el-select>
    </div>

    <div style="margin-top: 20px;">
      <el-select v-model="value5" multiple placeholder="请选择">
        <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value"></el-option>
      </el-select>
      <el-select v-model="value6" multiple collapse-tags style="margin-left: 20px;" placeholder="请选择">
        <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value"></el-option>
      </el-select>
    </div>

    <div style="margin-top: 20px;">
      <el-select v-model="value7" placeholder="请选择">
        <el-option v-for="item in cities" :key="item.value" :label="item.label" :value="item.value">
          <span style="float: left;">{{ item.label }}</span>
          <span style="float: right; color: #8492a6; font-size: 13px;">{{ item.value }}</span>
        </el-option>
      </el-select>

      <el-select v-model="value8" placeholder="请选择" style="margin-left: 20px;">
        <el-option-group v-for="group in options3" :key="group.label" :label="group.label">
          <el-option v-for="item in group.options" :key="item.value" :label="item.label" :value="item.value"></el-option>
        </el-option-group>
      </el-select>
    </div>

    <div style="margin-top: 20px;">
      <el-select v-model="value9" filterable placeholder="请选择">
        <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value"></el-option>
      </el-select>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      options: [
        {
          value: '选项1',
          label: '黄金糕'
        }, {
          value: '选项2',
          label: '双皮奶',
          disabled: true
        }, {
          value: '选项3',
          label: '蚵仔煎'
        }, {
          value: '选项4',
          label: '龙须面'
        }, {
          value: '选项5',
          label: '北京烤鸭'
        }
      ],
      cities: [
        {
          value: 'Beijing',
          label: '北京'
        },{
          value: 'Shanghai',
          label: '上海'
        },{
          value: 'Nanjing',
          label: '南京'
        },{
          value: 'Chengdu',
          label: '成都'
        },{
          value: 'Shenzhen',
          label: '深圳'
        },{
          value: 'Guangzhou',
          label: '广州'
        }
      ],
      options3: [
        {
          label: '热门城市',
          options: [
            {
              value: 'Shanghai',
              label: '上海'
            },{
              value: 'Beijing',
              label: '北京'
            }
          ]
        },{
          label: '城市名',
          options: [
            {
              value: 'Chengdu',
              label: '成都'
            },{
              value: 'Shenzhen',
              label: '深圳'
            },{
              value: 'Guangzhou',
              label: '广州'
            },{
              value: 'Changsha',
              label: '长沙'
            }
          ]
        }
      ],
      value: '',
      value2: '',
      value3: '',
      value4: '',
      value5: [],
      value6: [],
      value7: '',
      value8: '',
      value9: ''
    };
  },
  methods: {

  },
  mounted() {
  }
}
</script>
<style>
</style>
