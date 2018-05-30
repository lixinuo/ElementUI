<template>
  <div>
    <div class="top">
      <el-switch v-model="value1" active-color="#13ce66" inactive-color="#ff4949"></el-switch>
    </div>

    <div class="top">
      <el-switch v-model="value2" active-text="按月计费" inactive-text="按年计费"></el-switch>
    </div>

    <div class="top">
      <el-switch v-model="value3" active-text="按月计费" active-color="#13ce66" inactive-text="按年计费" inactive-color="#ff4949"></el-switch>
    </div>

    <div class="top">
      <el-tooltip :content="'Switch-value:' + value4 " placement="top">
        <el-switch v-model="value4" active-color="#13ce66" inactive-color="#ff4949" active-value="100" inactive-value="0"></el-switch>
      </el-tooltip>
    </div>


  </div>
</template>

<script>
export default {
  data () {
    return {
      value1: true,
      value2: true,
      value3: false,
      value4: '100'
    }
  },
  methods: {

  },
  mounted() {
  }
}
</script>
<style>
.top { margin-top: 20px; }
</style>
