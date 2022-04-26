<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="180px">
      <el-form-item label="Satellite name" style="width: 50%">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item label="Satellite company" style="width: 50%">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item label="Satellite company email" style="width: 50%">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item label="Satellite API" style="width: 50%">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item label="Satellite API Token" style="width: 50%">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">Create</el-button>
        <el-button @click="onCancel">Cancel</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: "",
        region: "",
        date1: "",
        date2: "",
        delivery: false,
        type: [],
        resource: "",
        desc: "",
      },
    };
  },
  methods: {
    onSubmit() {
      this.$message("submit!");
    },
    onCancel() {
      this.$message({
        message: "cancel!",
        type: "warning",
      });
    },
  },
};
</script>

<style scoped>
.line {
  text-align: center;
}
</style>
