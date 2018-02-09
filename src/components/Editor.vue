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
        <li v-for="i in [0,1,2,3,4,5,6]"
          v-bind:class="{active:currentTab === i}" @click="currentTab = i">
                Tab{{i}}
        </li>
        <!-------<li v-bind:class="{active:currentTab === 0}" @click="currentTab = 0">tab1</li>
         <li  v-bind:class="{active:currentTab === 1}" @click="currentTab = 1">tab2</li>
         <li  v-bind:class="{active:currentTab === 2}" @click="currentTab = 2">tab3</li>
         <li  v-bind:class="{active:currentTab === 3}" @click="currentTab = 3">tab4</li>
         <li  v-bind:class="{active:currentTab === 4}" @click="currentTab = 4">tab5</li>
         <li  v-bind:class="{active:currentTab === 5}" @click="currentTab = 5">tab6</li>
         <li  v-bind:class="{active:currentTab === 6}" @click="currentTab = 6">tab7</li>
 ----------->
      </ol>
    </nav>
  </div>
</template>
<script>
  export default {
    data(){
      return{
        currentTab:0,
        icons:['idcard','work','school','code','interst','phone','add']
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
    box-shadow:inset 0 1px 3px 0 rgba(0,0,0,0.25);

    #editor_nav{
      width:20%;
      height:inherit;
      background:#1f2126;
      border-bottom-left-radius: 4px;
      border-top-left-radius: 4px;

       li{
         width:100%;
         height:48px;
         margin-bottom: 16px;
         margin-top: 16px;
         border:1px solid red;
         text-align: center;
         line-height: 48px;
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
       }

    }
    #editor_form{
      width:80%;
      height:inherit;
      ol li{
        display: none;
        &.active{
          display: block;
        }
      }
    }

  }

</style>
