<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="180px">
      <el-form-item label="ミッション期間計画" style="width: 50%">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item label="イベント情報設定" style="width: 30%">
      <el-row>
      <el-col >
      <el-input v-model="form.name" />
      <el-button
        v-waves
        class="filter-item"
        type="primary"
        icon="el-icon-search"
        @click="handleFilter"
      >
        検索
      </el-button>
      </el-col>
      </el-row>
      </el-form-item>

      <el-form-item label="撮影イベント設定" style="width: 30%">
      <el-input v-model="form.name" />
      <el-button
        v-waves
        class="filter-item"
        type="primary"
        icon="el-icon-search"
        @click="handleFilter"
      >
        検索
      </el-button>
      </el-form-item>
      <el-form-item label="メンテナンス設定" style="width: 30%">
      <el-input v-model="form.name" />
      <el-button
        v-waves
        class="filter-item"
        type="primary"
        icon="el-icon-search"
        @click="handleFilter"
      >
        検索
      </el-button>
      </el-form-item>
      <el-form-item label="一般ユーザー公開" style="width: 50%">
      <el-select
        value="公開"
        placeholder="Type"
        clearable
        class="filter-item"
        style="width: 130px"
      >
        <el-option value="All">すべて</el-option>
        <el-option value="Public">公開</el-option>
        <el-option value="Private">未公開</el-option>
      </el-select>      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">作成</el-button>
        <el-button @click="onCancel">キャンセル</el-button>
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
