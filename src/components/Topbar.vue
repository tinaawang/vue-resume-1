<template>
  <div id="topbar">
    <div id="topbar_logo">{{text}}</div>
  </div>
</template>
<script>
  export  default {
    name:'Topbar',
    data(){
      return{
        text:'Resume'
      }
    }
  }
</script>
<style>
  #topbar{
    border: 1px solid gray;
    max-width:1440px;
    min-width:1024px;
    padding: 16px 16px;
    height:64px;


  }
  #topbar>#topbar_logo{
    font-family:STHeitiSC-Light;
    font-size:24px;
    color:#000000;
    letter-spacing:0;
    line-height: 32px;
  }
</style>
