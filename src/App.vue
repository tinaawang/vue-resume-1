<template>
  <div id="app"  v-bind:class="{previewMode:previewMode}">
    <div class="wrapper">

      <Topbar class="topbar" v-on:preview="preview"></Topbar>

      <main>
        <Editor  v-bind:resume="resume" class="editor"></Editor>
        <Preview  v-bind:resume="resume" class="preview"></Preview>
      </main>
    </div>
    <el-button @click="exitPreview" id="exitPreview">退出预览</el-button>
  </div>
</template>

<script>
import Topbar from './components/Topbar'
import Editor from './components/Editor'
import Preview from './components/Preview'
export default {
  name: 'App',
  components: {
    Topbar,Editor,Preview
  },
  data() {
    return {
      previewMode:false,
      resume:{
        profile:{
          name:'',
          city:'',
          birth:''
        },
        workHistory:[
          {company:'',content:''},
        ],
        studyHistory:[
          {school:'',duration:'',degree:''}
        ],
        projectHistory:[{
          projectName:'',introduction:'',duration:''
        }],
        hobbies:[{
          hobby:''
        }],
        Information:{phone_number:'',WeiXin:'',email:'',address:''}
      }
    }


  },
  methods:{
    preview(){
      this.previewMode = true
    },
    exitPreview(){
      this.previewMode = false
    }
  }
}
</script>

<style>
  html,body,#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    height:100%;
    background: #dddddd;


  }



  .icon {
    width: 1em; height: 1em;
    fill: currentColor;
    vertical-align: -0.15em;
    overflow: hidden;
  }
  .wrapper{
    height:100%;
    display: flex;
    flex-direction: column;

  }
  .previewMode  #exitPreview{
    display: inline-block;
    position: fixed;
    bottom:20px;
    right:40px;

  }
  #exitPreview{
    display: none;
  }

  .topbar{
    background:#ffffff;
    box-shadow:0 1px 3px 0 rgba(0,0,0,0.25);
  }

  main{
    height:100%;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    margin: 0;
  }

  main > .editor {
    width: 35%;

    margin: 16px 8px 19px 16px;
  }

  main > .preview {
    width:65%;
    overflow: auto;
    margin:16px 16px 19px 8px;
  }
  .previewMode #topbar{
    display: none;
  }
  .previewMode #editor{
    display: none;
  }
</style>
