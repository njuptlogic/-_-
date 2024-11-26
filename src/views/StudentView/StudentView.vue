<template>
    <div class="container">
        <p style="display: flex;justify-content: end;padding: 0 20px;margin: 10px;">
            <el-button type="primary" @click="dialogFormVisible=true">新增学生</el-button>
        </p>
        <el-table :data="filterTableData" style="width: 100%">
            <el-table-column label="Id" prop="id" />
            <el-table-column label="姓名" prop="name" />
            <el-table-column label="账号" prop="account" />
            <el-table-column label="密码" prop="password" />
            <el-table-column label="班级" prop="class" />

            <el-table-column align="right">
                <template #header>
                    <el-input v-model="search" size="small" placeholder="Type to search" />
                </template>
                <template #default="scope">
                    <el-button size="small" @click="handleEdit(scope.$index, scope.row)">
                        编辑
                    </el-button>
                    <el-button size="small" type="danger" @click="handleDelete(scope.$index, scope.row)">
                        删除
                    </el-button>
                </template>
            </el-table-column>
        </el-table>
        <el-dialog v-model="dialogFormVisible" title="添加学生" width="500" style="padding: 10px 30px;">
            <el-form>
                <el-form-item label="姓名" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="账号" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="密码" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="班级" :label-width="formLabelWidth">
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
        <el-pagination size="small" background layout="prev, pager, next" :total="500" class="mt-4"
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
                    id: 1,
                    name: '张帅',
                    account: '202410001',
                    password: '202410002',
                    class: '202411C191',
                },
                {
                    id: 2,
                    name: '张帅',
                    account: '202410002',
                    password: '202410002',
                    class: '202411C194',
                },
                {
                    id: 3,
                    name: '张帅',
                    account: '202410003',
                    password: '202410002',
                    class: '202411C192',
                },
                {
                    id: 4,
                    name: '张帅',
                    account: '202410004',
                    password: '202410002',
                    class: '202411C191',
                },
                {
                    id: 5,
                    name: '张帅',
                    account: '202410006',
                    password: '202410002',
                    class: '202411C191',
                },
                {
                    id: 6,
                    name: '张帅',
                    account: '202410007',
                    password: '202410002',
                    class: '202411C192',
                },
                {
                    id: 7,
                    name: '张帅',
                    account: '202410008',
                    password: '202410002',
                    class: '202411C193',
                },
                {
                    id: 8,
                    name: '张帅',
                    account: '202410009',
                    password: '202410002',
                    class: '202411C192',
                },
                {
                    id: 9,
                    name: '张帅',
                    account: '202410010',
                    password: '202410002',
                    class: '202411C193',
                },
                {
                    id: 10,
                    name: '张帅',
                    account: '202410004',
                    password: '202410002',
                    class: '202411C192',
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