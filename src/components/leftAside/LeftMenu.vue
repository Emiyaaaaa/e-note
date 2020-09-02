<template>
  <component :is="menuComponent" />
</template>

<script>
import Select from "@/components/leftAside/Select";
import DateLeftMenu from "@/components/leftAside/leftMenu/DateLeftMenu";
import DirectoryLeftMenu from "@/components/leftAside/leftMenu/DirectoryLeftMenu";

export default {
  name: "LeftMenu",
  props: {
    menuMap: {
      type: Map,
      default() {}
    },
    menuComponent: {
      type: String,
      default() {}
    }
  },
  components: {
    DirectoryLeftMenu,
    DateLeftMenu,
    Select
  }
};
</script>

<style scoped></style>
