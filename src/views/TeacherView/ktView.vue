<template>
    <div class="container">
        <p style="display: flex;justify-content: end;padding: 0 20px;margin: 10px;">
            <el-button type="primary" @click="dialogFormVisible = true">新增课题</el-button>
        </p>
        <el-table :data="filterTableData" style="width: 100%">
            <el-table-column label="课题编号" prop="课题编号" />
            <el-table-column label="课题类型" prop="课题类型" />
            <el-table-column label="课题名称" prop="课题名称" />
            <el-table-column label="结束时间" prop="结束时间" />
            <el-table-column label="选题人数" prop="选题人数" />

            <el-table-column align="right">
                <template #header>
                    <el-input v-model="search" size="small" placeholder="Type to search" />
                </template>
                <template #default="scope">
                    <el-button type="primary" size="small" @click="handleEdit(scope.$index, scope.row)">
                        查看详情
                    </el-button>
                </template>
            </el-table-column>
        </el-table>
        <el-dialog v-model="dialogFormVisible" title="添加学生" width="500" style="padding: 10px 30px;">
            <el-form>
                <el-form-item label="课题名称" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="授课教师" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="研究方向" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="截止日期" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>

            </el-form>
            <template #footer>
                <div class="dialog-footer">
                    <el-button @click="dialogFormVisible = false">取消</el-button>
                    <el-button type="primary" @click="dialogFormVisible = false">
                        确认
                    </el-button>
                </div>
            </template>
        </el-dialog>
        <el-pagination size="small" background layout="prev, pager, next" :total="2" class="mt-4"
            style="display: flex;justify-content: end;padding: 20px" />
    </div>
</template>

<script>
export default {
    name: 'StudentView',
    data() {
        return {
            dialogFormVisible: false,
            tableData: [
                {
                    "课题编号": 27465,
                    "课题类型": "计算机科学",
                    "课题名称": "分布式系统设计",
                    "结束时间": "2025-04-15",
                    "密码": "a4s7d8f2",
                    "选题人数": 32
                },{
                    "课题编号": 58126,
                    "课题类型": "计算机科学",
                    "课题名称": "数据库原理",
                    "结束时间": "2025-03-31",
                    "密码": "asawqwq",
                    "选题人数": 48
                }]
        }
    },
    computed: {
        filterTableData: function () {
            return this.tableData;
        }
    },
    methods: {
        handleEdit(index, row) {
            console.log(index, row);
        },
        handleDelete(index, row) {
            console.log(index, row);
        }
    }
}
</script>

<style lang="scss" scoped></style>