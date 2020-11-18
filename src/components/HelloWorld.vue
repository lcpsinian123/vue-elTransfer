<template>
<div class="elTransfer">
    <div class="leftContainer">
        <slot name="leftTopSlot"> </slot>
        <el-table ref="multipleTable" :data="tableData" tooltip-effect="dark" style="width: 100%" @selection-change="handleSelectionChange">
            <el-table-column type="selection" width="55">
            </el-table-column>
            <el-table-column label="日期" width="120">
                <template slot-scope="scope">{{ scope.row.date }}</template>
            </el-table-column>
            <el-table-column prop="name" label="姓名" width="120">
            </el-table-column>
            <el-table-column prop="address" label="地址" show-overflow-tooltip>
            </el-table-column>
        </el-table>
        <div class="pagesBox">
            <el-pagination @size-change="handleSizeChange" @current-change="handleCurrentChange" :current-page="currentPage4" :page-sizes="[100, 200, 300, 400]" :page-size="100" layout="total, sizes, prev, pager, next, jumper" :total="400">
            </el-pagination>
        </div>
    </div>
    <div class="middleContainer">
          <div class="btn"> 
            <el-button :disabled="isSelectDiabled" size="mini">选择 <i class="el-icon-arrow-right"></i></el-button>
          </div>
          <div class="btn">
            <el-button :disabled="removeDisable" size="mini">移除 <i class="el-icon-arrow-left"></i></el-button>
          </div>
    
    </div>
    <div class="rightContainer">
      <slot name="RightTopSlot"></slot>
        <el-table ref="multipleTable" :data="tableData" tooltip-effect="dark" style="width: 100%" @selection-change="handleSelectionChange">
            <el-table-column type="selection" width="55">
            </el-table-column>
            <el-table-column label="日期" width="120">
                <template slot-scope="scope">{{ scope.row.date }}</template>
            </el-table-column>
            <el-table-column prop="name" label="姓名" width="120">
            </el-table-column>
            <el-table-column prop="address" label="地址" show-overflow-tooltip>
            </el-table-column>
        </el-table>
        <div class="pagesBox">
            <el-pagination @size-change="handleSizeChange" @current-change="handleCurrentChange" :current-page="currentPage4" :page-sizes="[100, 200, 300, 400]" :page-size="100" layout="total, sizes, prev, pager, next, jumper" :total="400">
            </el-pagination>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: 'HelloWorld',
    props: {
        msg: String,
        removeDisable:{
          type:Boolean,
          required:true
        },
        isSelectDiabled:{
          type:Boolean,
          required:true
        },
    },
    data() {
        return {
            tableData: [{
                date: '2016-05-03',
                name: '王小虎',
                address: '上海市普陀区金沙江路 1518 弄'
            }, {
                date: '2016-05-02',
                name: '王小虎',
                address: '上海市普陀区金沙江路 1518 弄'
            }, {
                date: '2016-05-04',
                name: '王小虎',
                address: '上海市普陀区金沙江路 1518 弄'
            }, {
                date: '2016-05-01',
                name: '王小虎',
                address: '上海市普陀区金沙江路 1518 弄'
            }, {
                date: '2016-05-08',
                name: '王小虎',
                address: '上海市普陀区金沙江路 1518 弄'
            }, {
                date: '2016-05-06',
                name: '王小虎',
                address: '上海市普陀区金沙江路 1518 弄'
            }, {
                date: '2016-05-07',
                name: '王小虎',
                address: '上海市普陀区金沙江路 1518 弄'
            }],
            multipleSelection: [],
        }
    },
      methods: {
      handleSizeChange(val) {
        console.log(`每页 ${val} 条`);
      },
      handleCurrentChange(val) {
        console.log(`当前页: ${val}`);
      }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped  >
.elTransfer {
    width: 100%;
    height: 100%;
    background: skyblue;
    display: flex;
}
.middleContainer{
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}

/* h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
} */
</style>
