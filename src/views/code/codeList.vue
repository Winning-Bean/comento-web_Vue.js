<template>
  <div>
    <layout/>
      <div class="divLeft mt10">
        <el-input v-model="form.name" placeholder="코드명" style="width:90%"></el-input>
        <el-button @click="doList" type="primary">조회</el-button>
      </div>

      <el-card class="box-card mt10">
        <div slot="header" class="clearfix" style="text-align:left">
          <span>대표코드</span>
        </div>
        <el-row type="flex">
          <el-table :data="noticeList" border highlight-current-row @row-click="rowSel" height="300">
            <el-table-column align="center" label="코드" width="150">
              <template slot-scope="scope">
                {{scope.row.seqNo}}
              </template>
            </el-table-column>
            <el-table-column align="center" label="코드명" width="150">
              <template slot-scope="scope">
                {{scope.row.seqNo}}
              </template>
            </el-table-column>
            <el-table-column label="코드영문명" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.viewCnt}}
              </template>
            </el-table-column>
            <el-table-column label="코드순서" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.regDttm}}
              </template>
            </el-table-column>
            <el-table-column label="사용여부" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.regDttm}}
              </template>
            </el-table-column>
            <el-table-column label="연결코드1" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.regDttm}}
              </template>
            </el-table-column>
            <el-table-column label="연결코드2" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.regDttm}}
              </template>
            </el-table-column>
            <el-table-column label="연결코드3" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.regDttm}}
              </template>
            </el-table-column>
          </el-table>
        </el-row>
      </el-card>

      <el-card class="box-card mt10">
        <div slot="header" class="clearfix" style="text-align:left">
          <span>상세코드</span>
        </div>
        <el-row type="flex">
          <el-table :data="noticeList" border highlight-current-row @row-click="rowSel" height="300">
            <el-table-column align="center" label="대표코드" width="100">
              <template slot-scope="scope">
                {{scope.row.seqNo}}
              </template>
            </el-table-column>
            <el-table-column align="center" label="코드" width="100">
              <template slot-scope="scope">
                {{scope.row.seqNo}}
              </template>
            </el-table-column>
            <el-table-column label="코드명" align="center" width="100">
              <template slot-scope="scope">
                {{scope.row.viewCnt}}
              </template>
            </el-table-column>
            <el-table-column label="코드영문명" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.regDttm}}
              </template>
            </el-table-column>
            <el-table-column label="코드순서" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.regDttm}}
              </template>
            </el-table-column>
            <el-table-column label="사용여부" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.regDttm}}
              </template>
            </el-table-column>
            <el-table-column label="연결코드1" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.regDttm}}
              </template>
            </el-table-column>
            <el-table-column label="연결코드2" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.regDttm}}
              </template>
            </el-table-column>
            <el-table-column label="연결코드3" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.regDttm}}
              </template>
            </el-table-column>
          </el-table>
        </el-row>
      </el-card>
  </div>
</template>

<script>
import layout from '@/views/layout/Layout'

export default {
  name: 'CodeList',
  components: { layout },
  data () {
    return {
      form: {
        subject: '',
        statCd: ''
      },
      noticeList: [],
      noticeForm: {},
      ui: 'html'
    }
  }
}
</script>
