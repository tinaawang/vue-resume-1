<template>
  <div>

    <el-form  :label-position="labelPosition"  label-width="50px" >
      <div class="container" v-for="(item,index) in items" v-bind:key="index" >
        <el-form-item v-bind:label="label[key] || key" v-for="key in keys" v-bind:key="key" >
          <el-input v-model="item[key]"></el-input>

        </el-form-item>

        <i class="el-icon-delete" @click="removeItem(index)"></i><!--这时候就绑定了index，数组和渲染顺序一致--->
        <el-button :plain="true" @click="error" style="display: none;">错误</el-button>
      </div>

      <el-button type="success" @click="addItem">Add</el-button>
    </el-form>
  </div>
</template>

<script>
  export  default {
    props:['items','labelPosition','label'],

    computed:{
      keys(){

        return Object.keys(this.items[0])  /*这里遗留一个bug,不能剩余一个空对象*/

        /*因为items声明的时候是一个数组，里面默认放一个对象*/
      }

    },
    methods:{

      addItem() {
        const i = [];
        this.keys.map((key) => {
          i[key] = ''
        })
        this.items.push(i)
      },
      error() {
        this.$message.error('个数不能小于1哦');
      },
      removeItem(index){
        if(this.items.length < 2){
          this.error()
        }
        else{this.items.splice(index,1)}

      }
    }
  }
</script>
