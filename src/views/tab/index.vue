<template>
<el-container style="min-height:1000px;height:100%">
  <el-aside width="">
    <div class="menu">
        <div style="height:45px;padding-top: 15px;background: #7d8ec3;">
          <el-button style="margin-left: 5px;padding: 5px 10px" plain :icon="[isCollapse==true ?'el-icon-d-arrow-right':'el-icon-d-arrow-left']" @click="openclose"></el-button>
          <span class="menutitle" v-if = "isCollapse === false" >SAGIRI管理平台</span>
        </div>
        <el-menu default-active="1-4-1" class="el-menu-vertical-demo" :collapse="isCollapse" :collapse-transition=false>
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span slot="title">导航一</span>
            </template>
            <el-menu-item-group>
              <el-menu-item @click="addtab" index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
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

    </el-header>
    {{aaaa}}
    <el-main>
        <el-tabs v-model="editableTabsValue" type="card" closable>
          <el-tab-pane
            :key="item.name"
            v-for="(item, index) in editableTabs"
            :label="item.title"
            :name="item.name"
          >
            {{item.content}}
          </el-tab-pane>
        </el-tabs>
    </el-main>
    <el-footer>Footer</el-footer>
  </el-container>
</el-container>
</template>

<script>
export default {
  data () {
    return {
      aaaa: this.$store.state.example,
      isCollapse: false,
      tip: '收起',
      menutitle: 'sagiri',
      editableTabsValue: '2',
      editableTabs: [{
        title: 'Tab 1',
        name: '1',
        content: 'Tab 1 content'
      }, {
        title: 'Tab 2',
        name: '2',
        content: 'Tab 2 content'
      }],
      tabIndex: 2,
      menu:[{
      }]
    }
  },
  methods: {
    addtab () {
      let tab = {
        title: 'Tab 3',
        name: '3',
        content: 'http://www.baidu.com'
      }
      this.editableTabs.push(tab)
    },
    openclose () {
      this.isCollapse = !this.isCollapse
      this.tip = this.isCollapse ? '展开' : '收起'
    },
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
span{
    font-family: "PingFang SC";
}
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
    max-width:300px;
    background-color: rgb(255, 255, 255);
    color: #333;
    text-align: left;
  }

  .el-main {
    /* background-color: #E9EEF3; */
    color: #333;
    text-align: center;
    border: solid 1px #e6e6e6;
    /* line-height: 160px; */
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
  .el-submenu {
    min-width: 200px;
    list-style: none;
    margin: 0;
    padding-left: 0;
  }
  .menutitle{
    font-family: Microsoft YaHei;
    font-weight: 600;
    font-size: 17px;
    color: #E6E6E6;
  }
</style>
