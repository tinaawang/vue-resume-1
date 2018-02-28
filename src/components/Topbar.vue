<template>
  <div id="topbar">
    <div id="topbar_logo">{{text}}</div>
    <div class="actions">
    <!---<el-button type="primary">登录</el-button>---->
     <!----<el-button type="success">注册</el-button>---->
      <el-button type="success" @click="preview">预览</el-button>
    </div>
  </div>
</template>
<script>
  export  default {
    name:'Topbar',
    data(){
      return{
        text:'Resume'
      }
    },
    methods:{
      preview(){
        this.$emit('preview')
      }
    }
  }
</script>
<style lang="scss">
  #topbar{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    border: 1px solid gray;
    max-width:1440px;
    min-width:1024px;
    padding: 16px 16px;
    height:64px;

  }

  #topbar {
    #topbar_logo {
      font-family: STHeitiSC-Light;
      font-size: 24px;
      color: #000000;
      letter-spacing: 0;
      line-height: 32px;
    }
  }
</style>
