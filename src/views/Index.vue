<template>
  <!-- 进入界面 -->
  <div>
    <!-- <div class="header"></div> -->
    <!-- 内容 -->
    <div class="contain">
      <div class="title">
        <div class="title-item">
          <div>
            <img src="../assets/image/img-b155b7.png" alt />
          </div>
          <div style="font-size:28px">智能枪支弹药专用保险柜</div>
          <div style="font-size:38px">管理系统</div>
        </div>
      </div>
      <div class="cur-date">
        <div class="title-item">
          <div style="font-size:38px">{{currentDate}}</div>
          <div style="font-size:38px">{{currentTime}}</div>
        </div>
      </div>
    </div>
    <!-- 底部仪表盘 -->
    <div class="foot">
      <div class="dash-board">网络正常</div>
      <div class="dash-board">数据正常</div>
      <div class="dash-board">电源正常</div>
      <div class="dash-board">柜机正常</div>
      <div class="dash-board">30℃</div>
      <div class="dash-board">62%</div>
    </div>
    <!-- 底部 -->
  </div>
</template>

<script>
import { create } from "domain";
export default {
  data() {
    return {
      currentDate: "",
      currentTime: ""
    };
  },
  methods: {
    getCurrentDateTime() {
      let dateObj = new Date();
      let year = dateObj.getFullYear(); //得到年份
      let month = dateObj.getMonth(); //得到月份
      let date = dateObj.getDate(); //得到日期
      let hour = dateObj.getHours(); //得到小时
      let minu = dateObj.getMinutes(); //得到分钟
      let sec = dateObj.getSeconds(); //得到秒
      month = month + 1;
      if (month < 10) month = "0" + month;
      if (date < 10) date = "0" + date;
      if (hour < 10) hour = "0" + hour;
      if (minu < 10) minu = "0" + minu;
      if (sec < 10) sec = "0" + sec;
      this.currentDate = year + "年" + month + "月" + date + "日"
      this.currentTime = hour + ":" + minu + ":" + sec
    },
    goLogin() {
      this.$router.push({'name':'login'});
    },
    goApplication() {
      this.$router.push({'name':'application'});
    }
  },
  created() {
    this.getCurrentDateTime();
    window.setInterval(() => {
      this.getCurrentDateTime();
    }, 1000);
  }
};
</script>

<style>
* {
  padding: 0;
  margin: 0;
}
.foot {
  width: 100%;
  height: 40px;
  background: #7059ab;
  position: absolute;
  bottom: 0;
  padding: 2% 20%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  font-size: 18px;
  font-weight: 500;
  line-height: 1.1;
  align-items: center;
  color: #fff;
}
.contain {
  position: absolute;
  top: 0px;
  bottom: 40px;
  left: 0;
  right: 0;
  background: #5f4c9d;
  color: #fff;
  display: flex;
  flex-direction: row;
}
.title {
  width: 30%;
  text-align: center;
  margin-left: 18%;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}
.title img {
  width: 45%;
}
.cur-date {
  width: 30%;
  text-align: center;
  margin-left: 4%;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}
.title-item {
  width: 100%;
  height: 70%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  align-content: center;
  background: #7059ab;
  border-radius: 10px;
}
</style>