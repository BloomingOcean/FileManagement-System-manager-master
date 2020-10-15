<template>
  <div id="main-body">
    <div class="select-checkbox">
      <el-select v-model="period_value" placeholder="请选择期次">
        <el-option
          v-for="item in options_period"
          :key="item"
          :label="item"
          :value="item">
        </el-option>
      </el-select>
      <el-select v-model="situation" placeholder="请选择上传情况">
        <el-option
          v-for="item in upload_situation"
          :key="item"
          :label="item"
          :value="item">
        </el-option>
      </el-select>
      <el-button type="primary" @click="check" plain>查询</el-button>
    </div>
    <!-- 表格展示为上传信息 -->
    <el-table
      :data="class_info"
      stripe
      height="600"
      highlight-current-row
      style="width: 100%">
      <el-table-column
        align="center"
        prop="majorName"
        label="专业"
        width="550">
      </el-table-column>
      <el-table-column
        align="center"
        prop="classSequence"
        label="班级"
        width="550">
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
// import axios from 'axios'

export default {
  name: 'Dashboard',
  data() {
    return {
      server_config: 'http://49.234.17.88:7489',
      options_period: [],
      period_value: '',
      class_info: [],
      upload_situation: ['已上交', '未上交'],
      situation: '',
      computed: {
        ...mapGetters([
          'name'
        ])
      }
    }
  },
  // 页面初始化
  mounted: function() {
  },
  methods: {
  }
}
</script>

<style lang='scss' scoped>
.dashboard {
  &-container {
    margin: 30px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}
.select-checkbox {
  margin-bottom: 10px;
}
.choise-file {
  margin-bottom: 10px;
}
.info-option {
  margin-bottom: 20px;
}
</style>
