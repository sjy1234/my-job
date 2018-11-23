<template>
  <div class="box">
    <el-menu
    :default-active="activeIndex2"
    class="el-menu-demo"
    mode="horizontal"
    @select="handleSelect"
    background-color="#545c64"
    text-color="#fff"
    active-text-color="#ffd04b">  
    <el-col :span="4"><el-menu-item index="1">树下的猫</el-menu-item></el-col>
        <el-col :span="16" class="nav-center">
            <span>关于我</span>
            <span>慢生活</span>
            <span>留言板</span>
        </el-col>
    <el-col :span="4"></el-col>
    <el-menu-item index="4"><a href="https://www.ele.me" target="_blank">订单管理</a></el-menu-item>
    </el-menu>
    <!-- 中间部分开始 -->
    <div class="centre">
        <div class="centre-left">
            <!-- 这里放轮播图组件 -->
            <div class="lun">
              <!-- <el-carousel :interval="4000" arrow="always">
                <el-carousel-item v-for="(item,index) in images" :key="index">
                  <img :src="item.ti" alt="1">
                </el-carousel-item>
              </el-carousel> -->
                <el-carousel :interval="4000" type="card" height="200px">
                    <el-carousel-item v-for="(item,index) in images"  :key="index">
                    <img :src="item.ti" alt="1">
                    </el-carousel-item>
                </el-carousel>
            </div>
        </div>
        <div class="centre-right">
            <ul>
                <li></li>
                <li></li>
            </ul>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "index",
  props: [""],
  data() {
    return {
      activeIndex: "1",
      activeIndex2: "1",
      images:[
        { ti:require('../assets/images/1.jpg') },
        { ti:require('../assets/images/2.jpg') },
        { ti:require('../assets/images/3.jpg') },
        { ti:require('../assets/images/4.jpg') },
        { ti:require('../assets/images/5.jpg') },

      ]

    };
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    }
  }
};
</script>
<style lang='scss' scoped>
// .box{
//     width: 1226px;
//     margin: 0 auto;
// }
.nav-center {
  float: left;
  span {
    display: inline-block;
    height: 60px;
    line-height: 60px;
    color: aliceblue;
    padding: 0 30px;
    cursor: pointer;
    &:hover {
      background-color: #434a50;
    }
  }
}
.centre{
    width: 1226px;
    margin: 0 auto;
    margin-top: 30px;
    // background-color: #475669;
    .centre-left{
        width: 800px;
        // border: 1px solid #000;
        float: left;
    }
    .centre-right{
        width: 400px;
        height: 800px;
        border: 1px solid #000;
        float: right;
        ul li{
            height: 150px;
            background-color: pink;
        }
    }
}
.el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 200px;
    margin: 0;
  }
  
</style>