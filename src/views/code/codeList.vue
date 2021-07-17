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
          <el-table :data="codeList" border highlight-current-row @row-click="doDetailList" height="300">
            <el-table-column align="center" label="코드" width="180">
              <template slot-scope="scope">
                {{scope.row.commCdId}}
              </template>
            </el-table-column>
            <el-table-column align="center" label="코드명" width="180">
              <template slot-scope="scope">
                {{scope.row.commCdNm}}
              </template>
            </el-table-column>
            <el-table-column label="코드영문명" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.commCdEng}}
              </template>
            </el-table-column>
            <el-table-column label="코드순서" align="center" width="100">
              <template slot-scope="scope">
                {{scope.row.cdSort}}
              </template>
            </el-table-column>
            <el-table-column label="사용여부" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.cdUseYn}}
              </template>
            </el-table-column>
            <el-table-column label="연결코드1" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.conn1Cd}}
              </template>
            </el-table-column>
            <el-table-column label="연결코드2" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.conn2Cd}}
              </template>
            </el-table-column>
            <el-table-column label="연결코드3" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.conn3Cd}}
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
          <el-table :data="codeDetailList" border highlight-current-row height="300">
            <el-table-column align="center" label="대표코드" width="120">
              <template slot-scope="scope">
                {{scope.row.commCdId}}
              </template>
            </el-table-column>
            <el-table-column align="center" label="코드" width="120">
              <template slot-scope="scope">
                {{scope.row.cdId}}
              </template>
            </el-table-column>
            <el-table-column label="코드명" align="center" width="120">
              <template slot-scope="scope">
                {{scope.row.cdNm}}
              </template>
            </el-table-column>
            <el-table-column label="코드영문명" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.cdEng}}
              </template>
            </el-table-column>
            <el-table-column label="코드순서" align="center" width="100">
              <template slot-scope="scope">
                {{scope.row.cdSort}}
              </template>
            </el-table-column>
            <el-table-column label="사용여부" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.cdUseYn}}
              </template>
            </el-table-column>
            <el-table-column label="연결코드1" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.conn1Cd}}
              </template>
            </el-table-column>
            <el-table-column label="연결코드2" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.conn2Cd}}
              </template>
            </el-table-column>
            <el-table-column label="연결코드3" align="center" width="150">
              <template slot-scope="scope">
                {{scope.row.conn3Cd}}
              </template>
            </el-table-column>
          </el-table>
        </el-row>
      </el-card>
  </div>
</template>

<script>
import layout from '@/views/layout/Layout'
import {reqPost} from '@/api/tran'

export default {
  name: 'CodeList',
  components: { layout },
  data () {
    return {
      form: {
        subject: '',
        statCd: ''
      },
      codeList: [],
      codeDetailList: [],
      ui: 'html'
    }
  },
  methods: {
    doList () {
      reqPost('/code/selectCode', this.form).then(response => {
        this.codeList = response.data.list
      })
    },
    doDetailList () {
      reqPost('/code/selectRepCode', this.form).then(response => {
        this.codeDetailList = response.data.list
      })
    }
  }
}
</script>
