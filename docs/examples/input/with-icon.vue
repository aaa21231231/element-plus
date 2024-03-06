<template>  
  <el-form :model="form" label-width="120px">  
    <el-form-item label="数据">  
      <span v-if="!isEditing">{{ form.data }}</span>  
      <el-input v-else v-model="form.data" @input="handleInputChange"></el-input>  
      <el-button @click="toggleEdit" v-if="!isEditing">编辑</el-button>  
      <el-button @click="saveChanges" v-if="isEditing">保存</el-button>  
      <el-button @click="cancelEdit" v-if="isEditing">取消</el-button>  
    </el-form-item>  
  </el-form>  
</template>  
  
<script>  
export default {  
  data() {  
    return {  
      form: {  
        data: '初始数据',  
      },  
      isEditing: false,  
    };  
  },  
  methods: {  
    toggleEdit() {  
      this.isEditing = true;  
    },  
    saveChanges() {  
      // 在这里处理保存逻辑，例如发送请求到后端  
      console.log('保存数据:', this.form.data);  
      this.isEditing = false;  
    },  
    cancelEdit() {  
      // 在这里处理取消编辑的逻辑，例如恢复到原始数据  
      this.isEditing = false;  
    },  
    handleInputChange() {  
      // 可选的：处理输入变化事件，例如进行实时验证  
    },  
  },  
};  
</script>
