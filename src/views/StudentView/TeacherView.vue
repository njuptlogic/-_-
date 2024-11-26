<template>
    <div class="container">
        <p style="display: flex;justify-content: end;padding: 0 20px;margin: 10px;">
        </p>
        <div style="padding: 20px;">
            <p>
                <span>
                    课题编号：
                </span>
                <span>
                    58309
                </span>
            </p>
            <p>
                <span>
                    课题名：
                </span>
                <span>
                    目标检测与识别
                </span>
            </p>
            <p>
                <span>
                    课题类型：
                </span>
                <span>
                    人工智能
                </span>
            </p>
            <p>
                <span>
                    课题描述：
                </span>
                <span>
                    AI人工智能
                </span>
            </p>
            <p>
                <span>
                    截止日期：
                </span>
                <span>
                    2024-12-31 00:00:00
                </span>
            </p>
            <p>
                <span>
                    考核分数：
                </span>
                <span style="color: red;">
                    90
                </span>
            </p>
        </div>
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
                <el-form-item label="级别" :label-width="formLabelWidth">
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
                    password: '密码',
                    class: '讲师',
                },
                {
                    id: 2,
                    name: '张帅',
                    account: '202410002',
                    password: '202410002',
                    class: '教授',
                },
                {
                    id: 3,
                    name: '张帅',
                    account: '202410003',
                    password: '202410002',
                    class: '教授',
                },
                {
                    id: 4,
                    name: '张帅',
                    account: '202410004',
                    password: '202410002',
                    class: '教授',
                },
                {
                    id: 5,
                    name: '张帅',
                    account: '202410006',
                    password: '202410002',
                    class: '副教授',
                },
                {
                    id: 6,
                    name: '张帅',
                    account: '202410007',
                    password: '202410002',
                    class: '副教授',
                },
                {
                    id: 7,
                    name: '张帅',
                    account: '202410008',
                    password: '202410002',
                    class: '副教授',
                },
                {
                    id: 8,
                    name: '张帅',
                    account: '202410009',
                    password: '202410002',
                    class: '副教授',
                },
                {
                    id: 9,
                    name: '张帅',
                    account: '202410010',
                    password: '202410002',
                    class: '副教授',
                },
                {
                    id: 10,
                    name: '张帅',
                    account: '202410004',
                    password: '202410002',
                    class: '讲师',
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

<style lang="scss" scoped>
p{
    span{
        &:nth-child(1){
            font-weight: 700;
        }
    }
}
</style>