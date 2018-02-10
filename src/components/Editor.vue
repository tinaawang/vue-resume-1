<template>
  <div id="editor">
   <nav id="editor_nav">
     <ol>
       <li v-for="i in [0,1,2,3,4,5,6]"
           v-bind:class="{active: currentTab === i}" v-on:click="currentTab = i">
         <svg class="icon" aria-hidden="true">
           <use v-bind:xlink:href="`#icon-${icons[i]}`"></use>
         </svg>
       </li>
      <!--- <li v-bind:class="{active: currentTab === 0}" v-on:click="currentTab = 0">
         <svg class="icon" >
           <use xlink:href="#icon-idcard"></use>
         </svg>
       </li>
       <li v-bind:class="{active: currentTab === 1}" v-on:click="currentTab = 1">
         <svg class="icon">
           <use xlink:href="#icon-work"></use>
         </svg>
       </li>
       <li v-bind:class="{active: currentTab === 2}" v-on:click="currentTab = 2">
         <svg class="icon">
           <use xlink:href="#icon-school"></use>
         </svg>
       </li>
       <li v-bind:class="{active: currentTab === 3}" v-on:click="currentTab = 3">
         <svg class="icon" >
           <use xlink:href="#icon-code"></use>
         </svg>
       </li>
       <li v-bind:class="{active: currentTab === 4}" v-on:click="currentTab = 4">
         <svg class="icon" aria-hidden="true">
           <use xlink:href="#icon-interst"></use>
         </svg>
       </li>
       <li v-bind:class="{active: currentTab === 5}"  v-on:click="currentTab = 5">
         <svg class="icon" aria-hidden="true">
           <use xlink:href="#icon-phone"></use>
         </svg>
       </li>
       <li v-bind:class="{active: currentTab === 6}" v-on:click="currentTab = 6">
         <svg class="icon" aria-hidden="true">
           <use xlink:href="#icon-add"></use>
         </svg>
       </li>
       --->
     </ol>
   </nav>
    <nav id="editor_form">
      <ol>
        <!-------  <li v-for="i in [0,1,2,3,4,5,6]"
            v-bind:class="{active:currentTab === i}" @click="currentTab = i">

          </li>
          ----------->
          <li v-bind:class="{active:currentTab === 0}" @click="currentTab = 0">
            <h2>个人信息</h2>
            <singleEditor v-bind:items="profile" v-bind:label="{name:'姓名',city:'城市',birth:'出生年月'}" v-bind:labelPosition="labelPosition"/>
          </li>
           <li  v-bind:class="{active:currentTab === 1}" @click="currentTab = 1">
             <h2>工作经历</h2>
             <ArrayEditor v-bind:labelPosition="labelPosition" v-bind:items="workHistory" v-bind:label="{company:'公司',content:'工作经历'}" />
           </li>
           <li  v-bind:class="{active:currentTab === 2}" @click="currentTab = 2">
             <h2>学习经历</h2>
             <ArrayEditor v-bind:labelPosition=" labelPosition" v-bind:items="studyHistory" v-bind:label="{school:'学习',duration:'时间',degree:'学位'}"/>
           </li>
           <li  v-bind:class="{active:currentTab === 3}" @click="currentTab = 3">
             <h2>项目经历</h2>
             <ArrayEditor v-bind:labelPosition=" labelPosition" v-bind:items="projectHistory" v-bind:label="{projectName:'项目名称',introduction:'项目简介',duration:'时间'}"/>
           </li>
           <li  v-bind:class="{active:currentTab === 4}" @click="currentTab = 4">
             <h2>兴趣爱好</h2>
             <ArrayEditor v-bind:labelPosition=" labelPosition" v-bind:items="interest" v-bind:label="{interest:`我的兴趣`}"/>
           </li>
           <li  v-bind:class="{active:currentTab === 5}" @click="currentTab = 5">
             <h2>联系方式</h2>
             <singleEditor v-bind:labelPosition=" labelPosition" v-bind:items="Information" v-bind:label="{phone_number:'电话',email:'邮箱',address:'地址'}"/>
           </li>
           <li  v-bind:class="{active:currentTab === 6}" @click="currentTab = 6">tab7</li>

      </ol>
    </nav>
  </div>
</template>
<script>
  import singleEditor from './singleEditor.vue'
  import ArrayEditor from './ArrayEditor.vue'

  export default {
    components:{ArrayEditor,singleEditor},
    data(){
      return{
        currentTab:0,
        labelPosition:'top',
        icons:['idcard','work','school','code','interst','phone','add'],
        profile:[{
          name:'',
          city:'',
          birth:''

        }],
        workHistory:[
          {company:'',content:''},
        ],
        studyHistory:[
          {school:'',duration:'',degree:''}
        ],
        projectHistory:[{
          projectName:'',introduction:'',duration:''
        }],
        interest:[{
          interest:''
        }],
        Information:[{phone_number:'',email:'',address:''}]
      }
    }


  }
</script>
<style lang="scss">
  #editor {
    display: flex;
    flex-direction: row;
    flex: 1;
    height: 100%;
    background:#ffffff;
    border-radius: 4px;
    box-shadow: 0 1px 3px 0 rgba(0,0,0,0.25);

    #editor_nav{
      width:20%;
      height:inherit;
      background:#1f2126;
      border-bottom-left-radius: 4px;
      border-top-left-radius: 4px;

       li{
         width:100%;
         height:48px;
         margin-bottom: 8px;
         margin-top: 8px;
         padding:12px 8px;
         text-align: center;
         &.active{
           background: white;
           .icon{
             fill: black;
           }
         }

         .icon{
           width:24px;
           height:24px;
           fill: white;

         }
       },
    li:nth-child(1) {
      margin-top: 0px;
      border-top-left-radius: 4px;

    }

    }
    #editor_form{
      width:80%;
      height:inherit;
      ol{
        height: 100%;
        overflow: auto;
      }
      ol li{
        display: none;
        padding: 32px;
        height: 100%;
        overflow: auto;

        .container{
          position: relative;
          i{
            position: absolute;
            top:30px;
            right:0;
          }
          hr{
            margin-top:-16px;

          }
        }


        &.active {
          display: block;

        }





      }
    }

  }

</style>
