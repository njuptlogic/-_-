<template>
    <div class="container">
        <p style="display: flex;justify-content: end;padding: 0 20px;margin: 10px;">
        </p>
        <div style="padding: 0 20px;">
            <p>
                <span style="font-weight: 700;">
                    课题名称：
                </span>
                <span>
                    计算机科学
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
                <span>
                    90
                </span>
            </p>
        </div>
        <el-table :data="filterTableData" style="width: 100%">
            <el-table-column label="学号" prop="学号" />
            <el-table-column label="姓名" prop="姓名" />
            <el-table-column label="性别" prop="性别" />
            <el-table-column label="专业" prop="专业" />
            <el-table-column label="分数" prop="分数">
                <template #default="scope">
                    <div style="color: red;">
                        {{ scope.row.分数 }}
                    </div>
                </template>
            </el-table-column>

            <el-table-column align="right">
                <template #header>
                    <el-input v-model="search" size="small" placeholder="Type to search" />
                </template>
                <template #default="scope">
                    <el-button size="small" @click="handleEdit(scope.$index, scope.row)" type="primary">
                        打分
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
                    "姓名": "林宇",
                    "性别": "男",
                    "学号": 23467,
                    "专业": "计算机与科学",
                    "分数": 88
                },
                {
                    "姓名": "苏瑶",
                    "性别": "女",
                    "学号": 78932,
                    "专业": "计算机与科学",
                    "分数": 93
                },
                {
                    "姓名": "陈晨",
                    "性别": "男",
                    "学号": 12398,
                    "专业": "计算机与科学",
                    "分数": 79
                },
                {
                    "姓名": "周悦",
                    "性别": "女",
                    "学号": 56701,
                    "专业": "计算机与科学",
                    "分数": 82
                },
                {
                    "姓名": "张辉",
                    "性别": "男",
                    "学号": 90156,
                    "专业": "计算机与科学",
                    "分数": 75
                },
                {
                    "姓名": "王琳",
                    "性别": "女",
                    "学号": 34589,
                    "专业": "计算机与科学",
                    "分数": 90
                },
                {
                    "姓名": "李阳",
                    "性别": "男",
                    "学号": 78923,
                    "专业": "计算机与科学",
                    "分数": 77
                },
                {
                    "姓名": "赵婉",
                    "性别": "女",
                    "学号": 12378,
                    "专业": "计算机与科学",
                    "分数": 85
                },
                {
                    "姓名": "孙俊",
                    "性别": "男",
                    "学号": 45690,
                    "专业": "计算机与科学",
                    "分数": 72
                },
                {
                    "姓名": "吴敏",
                    "性别": "女",
                    "学号": 67812,
                    "专业": "计算机与科学",
                    "分数": 87
                }
            ]
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
p {
    span {
        &:nth-child(1) {
            font-weight: 700;
        }
    }
}
</style>