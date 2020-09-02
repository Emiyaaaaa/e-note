<template>
  <el-container direction="vertical">
    <!--传入目录选择器Map-->
    <Select :select-data="selectData" @select="select" />
    <LeftMenu :menu-component="menuComponent" :menu-map="selectData.map" />
  </el-container>
</template>

<script>
import Select from "@/components/leftAside/Select";
import LeftMenu from "@/components/leftAside/LeftMenu";

export default {
  name: "LeftAside",
  data() {
    return {
      selectData: {
        default: "分类",
        map: new Map([
          ["分类", "DirectoryLeftMenu"],
          ["日期", "DateLeftMenu"]
        ])
      },
      // 默认菜单
      menuComponent: ""
    };
  },
  // 根据默认key设置默认目录
  mounted() {
    this.menuComponent = this.selectData.map.get(this.selectData.default);
  },
  components: {
    LeftMenu,
    Select
  },
  methods: {
    select(option) {
      this.menuComponent = this.selectData.map.get(option);
    }
  }
};
</script>

<style scoped></style>
