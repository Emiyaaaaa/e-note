<template>
  <div class="home">
    <el-container>
      <el-aside width="auto" class="el-aside">
        <LeftAside />
      </el-aside>
      <el-main>
        <Main />
      </el-main>
    </el-container>
  </div>
</template>

<script>
// @ is an alias to /src
import Main from "@/components/Main";
import LeftAside from "@/components/LeftAside";

export default {
  name: "Home",
  components: {
    LeftAside,
    Main
  }
};
</script>

<style scoped>
.el-aside{
  min-width: 200px;
}
</style>
