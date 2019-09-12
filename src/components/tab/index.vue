<template>
<el-container style="min-height:1000px;height:100%">
  <el-aside width="">
    <div class="menu">
        <el-menu default-active="1-4-1" class="el-menu-vertical-demo" :collapse="isCollapse" :collapse-transition=false>
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span slot="title">导航一</span>
            </template>
            <el-menu-item-group>
              <span slot="title">分组一</span>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <span slot="title">选项4</span>
              <el-menu-item index="1-4-1">选项1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-menu-item index="2">
            <i class="el-icon-menu"></i>
            <span slot="title">导航二</span>
          </el-menu-item>
          <el-menu-item index="3">
            <i class="el-icon-setting"></i>
            <span slot="title">导航三</span>
          </el-menu-item>
        </el-menu>
      </div>
  </el-aside>
  <el-container>
    <el-header>
      <i :class="[isCollapse==true ?'el-icon-d-arrow-right':'el-icon-d-arrow-left']" @click="openclose"></i>
    </el-header>
    <el-main>
    </el-main>
    <el-footer>Footer</el-footer>
  </el-container>
</el-container>
</template>

<script>
export default {
    data() {
      return {
        isCollapse: false,
      };
    },
    methods: {
      openclose(){
        this.isCollapse = !this.isCollapse;
      }
      // menuIcon(){

      // }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 100%;
    min-height: 400px;
  }
.el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  .el-aside {
    /* max-width:300px;  */
    background-color: rgb(255, 255, 255);
    color: #333;
    text-align: center;
    line-height: 200px;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  body > .el-container {
    margin-bottom: 40px;
  }
  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }
  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
  .menu{
    width: 100%;
  }
</style>