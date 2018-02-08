<template>
  <div id="app">
    <div class="wrapper">

      <Topbar class="topbar"></Topbar>

      <main>
        <Editor class="editor"></Editor>
        <Preview class="preview"></Preview>
      </main>
    </div>

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
  .wrapper{
    height:100%;
    display: flex;
    flex-direction: column;

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

    margin-left: 16px;
    margin-top: 16px;
    margin-bottom: 19px;

  }

  main > .preview {

    margin-right: 16px;
    margin-top: 16px;
    margin-bottom: 19px;
  }
</style>
