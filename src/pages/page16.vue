<template>
  <div>
    <div>
      <el-input-number v-model="num1" @change="handleChange" :min="1" :max="10" label="描述文字"></el-input-number>
    </div>

    <div style="margin-top: 20px;">
      <el-input-number v-model="num2" :disabled="true"></el-input-number>
    </div>

    <div style="margin-top: 20px;">
      <el-input-number v-model="num3" :step="2"></el-input-number>
    </div>

    <div style="margin-top: 20px;">
      <el-input-number v-model="num4" controls-position="right" @change="handleChange"></el-input-number>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      num1: 1,
      num2: 2,
      num3: 5,
      num4: 9
    };
  },
  methods: {
    handleChange(value) {
      console.log(value);
    }
  },
  mounted() {
  }
}
</script>
<style>
</style>
