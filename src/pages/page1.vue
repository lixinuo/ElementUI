<template>
  <div>
    <div>
      <el-input v-model="input" placeholder="请输入内容"></el-input>
    </div>

    <div style="margin-top: 20px;">
      <el-input v-model="input1" :disabled="true" placeholder="请输入内容"></el-input>
    </div>

    <div style="margin-top: 20px;">
      <el-input v-model="input2" clearable></el-input>
    </div>

    <div style="margin-top: 20px;">属性方式：
      <el-input v-model="input3" placeholder="请输入内容" suffix-icon="el-icon-date"></el-input>
      <el-input v-model="input4" placeholder="请输入内容" prefix-icon="el-icon-search"></el-input>
    </div>

    <div style="margin-top: 20px;">slot方式：
      <el-input v-model="input5" placeholder="请输入内容"><i slot="suffix" class="el-input__icon el-icon-date"></i></el-input>
      <div style="margin-top: 20px;"></div>
      <el-input v-model="input6" placeholder="请输入内容"><i slot="prefix" class="el-input__icon el-icon-search"></i></el-input>
    </div>

    <div style="margin-top: 20px;">
      <el-input v-model="textarea1" type="textarea" :row="2" placeholder="请输入内容"></el-input>
    </div>

    <div style="margin-top: 20px;">123
      <el-input type="textarea" autosize placeholder="请输入内容" v-model="textarea2" style="width: 200px;"></el-input>
      <div style="margin-top: 20px;"></div>
      <el-input type="textarea" :autosize="{ minRows: 2, maxRows: 4 }" placeholder="请输入内容" v-model="textarea3" style="width: 200px;"></el-input>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      input: '',
      input1: '',
      input2: '',
      input3: '',
      input4: '',
      input5: '',
      input6: '',
      textarea1: '',
      textarea2: '',
      textarea3: ''
    };
  },
  methods: {
  }
}
</script>
<style>
</style>
