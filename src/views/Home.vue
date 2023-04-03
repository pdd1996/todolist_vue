<template>
  <el-row :gutter="20">
    <el-col :span="4">
      <div class="grid-content bg-purple"></div>
    </el-col>
    <el-col :span="16">
      <el-container>
        <el-header>
          <span class="today">我的一天</span>
          <span class="time" id="time">时间</span>
        </el-header>
        <el-main>
          <el-table
            :data="tableData"
            style="width: 100%">
            <el-table-column
              prop="date"
              label="日期"
              width="180">
            </el-table-column>
          </el-table>
        </el-main>
        <el-footer>
          <el-input v-model="input" placeholder="添加todo项"></el-input>
          <el-button type="primary" icon="el-icon-plus" circle></el-button>
        </el-footer>
      </el-container>
    </el-col>
    <el-col :span="4">
      <div class="grid-content bg-purple"></div>
    </el-col>
  </el-row>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      tableData: []
    }
  }
};
</script>

<style scoped lang="less">

.container {
  height: 100vh;
}

.page_background {
  width: 100%;
  height: 100%;
  background: url("../assets/image/flower.jpg") no-repeat;
  background-size: cover;
  /* z-index: 100; */
}

.grid-content {
  border-radius: 4px;
  min-height: 36px;
}

</style>
