<template>
  <div>
    <h2>个人信息</h2>
    <el-form  :label-position="labelPosition"  label-width="50px" :model="profile">
      <el-form-item label="name">
        <el-input v-model="profile.name"></el-input>
      </el-form-item>
      <el-form-item label="city">
        <el-input v-model="profile.city"></el-input>
      </el-form-item>
      <el-form-item label="birth">
        <el-input v-model="profile.birth"></el-input>
      </el-form-item>
    </el-form>
  </div>

</template>

<script>
  export  default {
    props:['profile','labelPosition']



  }
</script>

<style></style>
