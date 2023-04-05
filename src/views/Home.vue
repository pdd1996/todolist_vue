<template>
  <div class="page_background">
    <el-row :gutter="20">
      <el-col :span="4">
        <div class="grid-content bg-purple"></div>
      </el-col>
      <el-col :span="16">
        <div class="content">
          <el-container>
            <el-header style="height: 250px">
              <span class="today">我的一天</span>
              <span class="time" id="time">{{ time }}</span>
            </el-header>
            <el-main>
              <el-table :data="todoList">
                <el-table-column prop="todoItem" label="todo"></el-table-column>
                <el-table-column fixed="right" label="操作" width="150">
                  >
                  <template slot-scope="scope">
                    <el-button
                      size="mini"
                      type="danger"
                      icon="el-icon-delete"
                      circle
                      @click="handleDelete(scope.$index, scope.row)"
                    ></el-button>
                  </template>
                </el-table-column>
              </el-table>
            </el-main>
            <el-footer>
              <el-input v-model="input" placeholder="添加任务项"></el-input>
              <el-button
                type="primary"
                icon="el-icon-plus"
                circle
                @click="handleClick"
              ></el-button>
            </el-footer>
          </el-container>
        </div>
      </el-col>
      <el-col :span="4">
        <div class="grid-content bg-purple"></div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import weekdays from "../assets/js/date.js";

export default {
  name: "Home",
  data() {
    return {
      time: "",
      input: "",
      todoList: [],
    };
  },
  methods: {
    showTime() {
      const date = new Date();
      const dayOfWeek = weekdays[date.getDay()];
      const month = date.getMonth() + 1;
      const day = date.getDate();
      this.time = month + "月" + day + "日，" + dayOfWeek;
    },
    handleClick() {
      const todoItem = this.input;
      if (todoItem !== "") {
        this.todoList.push({ todoItem });
        this.input = "";
      }
    },
    handleDelete(index, row) {
      console.log(index, row);
      this.todoList.splice(index, 1);
    },
  },
  mounted() {
    this.showTime();
  },
};
</script>

<style scoped lang="less">
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

.content {
  width: 100%;
  height: 100vh;
}

.el-header {
  text-align: left;
  padding-top: 7%;
  color: #fff;
}

.el-header .today {
  font-size: 64px;
}

.el-header .time {
  font-size: 32px;
  display: block;
}

.el-main {
  height: 550px;
}

.el-footer .el-input {
  width: 90%;
}

.el-footer .el-button {
  margin-left: 20px;
}
</style>
