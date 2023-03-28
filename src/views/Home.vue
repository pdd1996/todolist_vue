<template>
  <div class="container">
    <div class="page_background">
      <div class="top_bar">
        <div>
          <span class="today">我的一天</span>
          <span class="time" id="time">时间</span>
          <xxx-button type="danger">点击报名</xxx-button>
        </div>
      </div>
      <div class="content">
        <!--显示-->
        <ul class="list"></ul>
      </div>
      <div class="bottom_bar">
        <form>
          <label>
            <input type="text" placeholder="添加任务" />
            <button type="submit">添加</button>
          </label>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import { Button } from "xixixi-ui";
import "xixixi-ui/dist/xixixi-ui.css";

export default {
  name: "Home",
  components: {
    "xxx-button": Button,
  },
};
</script>

<style>
body {
  min-height: 100%;
  position: relative;
}

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

.top_bar {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 30%;
}

.top_bar div {
  padding-top: 5%;
  color: #fff;
}

.top_bar .today {
  font-size: 64px;
  margin: 0 0 0 20%;
}

.top_bar .time {
  font-size: 32px;
  display: block;
  margin: 10px 10% 0 20%;
}
.content {
  position: absolute;
  top: 30%;
  left: 0;
  right: 0;
  height: 50%;
}

.content ul {
  width: 60%;
  margin: 30px auto;
  list-style: none;
  padding: 0;
}

.content ul li {
  background-color: #f2f2f2;
  margin: 10px 0;
  border-radius: 5px;
  font-size: 28px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
}

.content ul li input {
  width: 40px;
  height: 40px;
  border-radius: 10px;
}

.content ul li span {
  flex: 1;
  margin-left: 22px;
}

.content ul li button {
  background-color: #e74c3c;
  color: #fff;
  border: none;
  padding: 5px 10px;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
  margin-left: 10px;
}

.content ul li.completed span {
  text-decoration: line-through;
  color: #aaa;
}

.content ul li.completed button {
  background-color: #ccc;
}

.bottom_bar {
  position: absolute;
  top: 75%;
  left: 0;
  right: 0;
  height: 25%;
}

.bottom_bar form {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.bottom_bar form label {
  width: 60%;
  margin: 0 auto;
}

.bottom_bar form input {
  width: 80%;
  min-width: 750px;
  height: 80px;
  padding: 10px 20px;
  border-radius: 5px;
  border: 1px solid #ccc;
  font-size: 32px;
}

.bottom_bar form button {
  width: 100px;
  height: 60px;
  margin-left: 20px;
  background-color: #e74c3c;
  color: #fff;
  border: none;
  padding: 5px 10px;
  border-radius: 10px;
  font-size: 28px;
  cursor: pointer;
}
</style>
