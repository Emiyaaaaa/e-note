<template>
  <el-col :span="24">
    <el-radio-group
      class="el-radio-group"
      v-model="radio"
      @input="$emit('select', radio)"
    >
      <el-radio-button
        v-for="key of selectData.map.keys()"
        :label="key"
        :key="key"
      ></el-radio-button>
    </el-radio-group>
  </el-col>
</template>

<script>
export default {
  name: "Select",
  props: {
    selectData: {
      type: Object,
      default() {}
    }
  },
  data() {
    return {
      radio: ""
    };
  },
  mounted() {
    // 设置默认值
    this.radio = this.selectData.default;
  }
};
</script>

<style scoped lang="scss">
.el-radio-group {
  width: 100%;
}
$active-width-proportion: 6/10;
.el-radio-group ::v-deep {
  .el-radio-button.is-active {
    width: percentage($active-width-proportion);
  }
  .el-radio-button:not(.is-active) {
    width: percentage(1-$active-width-proportion);
  }
  .el-radio-button {
    transition: width 0.1s ease-out;
    .el-radio-button__inner {
      width: 100%;
      padding: 6px;
    }
  }
}
</style>
