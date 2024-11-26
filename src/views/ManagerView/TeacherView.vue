<template>
    <div class="container">
        <p style="display: flex;justify-content: end;padding: 0 20px;margin: 10px;">
            <el-button type="primary" @click="dialogFormVisible = true">新增教师</el-button>
        </p>
        <el-table :data="filterTableData" style="width: 100%">
            <el-table-column label="工号" prop="工号" />
            <el-table-column label="姓名" prop="姓名" />
            <el-table-column label="性别" prop="性别" />
            <el-table-column label="专业" prop="专业" />
            <el-table-column label="账号" prop="账号" />
            <el-table-column label="密码" prop="密码" />

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
        <el-pagination size="small" background layout="prev, pager, next" :total="120" class="mt-4"
        style="display: flex;justify-content: end;padding: 20px" />
        <el-dialog v-model="dialogFormVisible" title="添加教师" width="500" style="padding: 10px 30px;">
            <el-form>
                <el-form-item label="工号" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="姓名" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="性别" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="专业" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="账号" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="密码" :label-width="formLabelWidth">
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
                    "姓名": "刘畅",
                    "性别": "男",
                    "工号": 27465,
                    "专业": "计算机科学",
                    "账号": "liuchang01",
                    "密码": "k4j8p3q7"
                },
                {
                    "姓名": "苏瑶",
                    "性别": "女",
                    "工号": 78531,
                    "专业": "金融",
                    "账号": "suyao12",
                    "密码": "n9m7r2t5"
                },
                {
                    "姓名": "许辉",
                    "性别": "男",
                    "工号": 19287,
                    "专业": "机械工程",
                    "账号": "xuhui23",
                    "密码": "b3g8v4y7"
                },
                {
                    "姓名": "冯琳",
                    "性别": "女",
                    "工号": 43720,
                    "专业": "教育学",
                    "账号": "fenglin34",
                    "密码": "p7l2k9n3"
                },
                {
                    "姓名": "马俊",
                    "性别": "男",
                    "工号": 85196,
                    "专业": "市场营销",
                    "账号": "majun45",
                    "密码": "s8d3f6h2"
                },
                {
                    "姓名": "朱婷",
                    "性别": "女",
                    "工号": 37058,
                    "专业": "医学",
                    "账号": "zhuting56",
                    "密码": "w2q7r4m9"
                },
                {
                    "姓名": "韩磊",
                    "性别": "男",
                    "工号": 62847,
                    "专业": "法学",
                    "账号": "hanlei67",
                    "密码": "z5x8c3v1"
                },
                {
                    "姓名": "秦悦",
                    "性别": "女",
                    "工号": 91736,
                    "专业": "艺术设计",
                    "账号": "qinyue78",
                    "密码": "l7n2p8g5"
                },
                {
                    "姓名": "谢峰",
                    "性别": "男",
                    "工号": 58309,
                    "专业": "化学工程",
                    "账号": "xiefeng89",
                    "密码": "t3b7y2k6"
                },
                {
                    "姓名": "唐婉",
                    "性别": "女",
                    "工号": 74218,
                    "专业": "心理学",
                    "账号": "tangwan90",
                    "密码": "r9m4v7f3"
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

<style lang="scss" scoped></style>