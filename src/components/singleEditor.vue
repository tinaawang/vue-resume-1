<template>
  <div>

    <el-form  :label-position="labelPosition"  label-width="50px" >
      <div class="container" v-for="(item,index) in items" v-bind:key="index" >
        <el-form-item v-bind:label="label[key] || key"  v-for="key in keys" v-bind:key="key" >
          <el-input v-model="item[key]"></el-input>

        </el-form-item>

      </div>


    </el-form>
  </div>
</template>

<script>
  export  default {
    props:['items','labelPosition','label'],
    computed:{
      keys(){

        return Object.keys(this.items)  /*这里遗留一个bug,不能剩余一个空对象*/

        /*因为items声明的时候是一个数组，里面默认放一个对象*/
      }

    }
  }
</script>
