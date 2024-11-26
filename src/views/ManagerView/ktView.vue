<template>
    <div class="container">
        <p style="display: flex;justify-content: end;padding: 0 20px;margin: 10px;">
            <el-button type="primary" @click="dialogFormVisible = true">新增课题</el-button>
        </p>
        <el-table :data="filterTableData" style="width: 100%">
            <el-table-column label="projectNumber" prop="projectNumber" />
            <el-table-column label="projectName" prop="projectName" />
            <el-table-column label="projectType" prop="projectType" />
            <el-table-column label="endTime" prop="endTime" />

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
        <el-dialog v-model="dialogFormVisible" title="添加课题" width="500" style="padding: 10px 30px;">
            <el-form>
                <el-form-item label="课题编号" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="课题名称" :label-width="formLabelWidth">
                    <el-input autocomplete="off" />
                </el-form-item>
                <el-form-item label="课题类型" :label-width="formLabelWidth">
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
        <el-pagination size="small" background layout="prev, pager, next" :total="70" class="mt-4"
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
                    "projectNumber": 27465,
                    "projectType": "计算机科学",
                    "projectName": "分布式系统设计",
                    "endTime": "2025-04-15",
                    "password": "a4s7d8f2"
                },
                {
                    "projectNumber": 78531,
                    "projectType": "经济学",
                    "projectName": "宏观经济模型分析",
                    "endTime": "2026-02-22",
                    "password": "g7h2j3k9"
                },
                {
                    "projectNumber": 19287,
                    "projectType": "机械设计",
                    "projectName": "新型机械传动机构研究",
                    "endTime": "2024-12-07",
                    "password": "m3n6p7q2"
                },
                {
                    "projectNumber": 43720,
                    "projectType": "教育学",
                    "projectName": "现代教育技术应用",
                    "endTime": "2025-07-03",
                    "password": "r8t4u2v5"
                },
                {
                    "projectNumber": 85196,
                    "projectType": "市场营销",
                    "projectName": "数字化营销模式创新",
                    "endTime": "2026-09-18",
                    "password": "w3x7y2z8"
                },
                {
                    "projectNumber": 37058,
                    "projectType": "临床医学",
                    "projectName": "心血管疾病治疗新方案",
                    "endTime": "2024-11-30",
                    "password": "c2d5e8f3"
                },
                {
                    "projectNumber": 62847,
                    "projectType": "法学",
                    "projectName": "知识产权保护研究",
                    "endTime": "2025-05-10",
                    "password": "k7l3m2n9"
                },
                {
                    "projectNumber": 91736,
                    "projectType": "艺术设计",
                    "projectName": "虚拟现实艺术创作",
                    "endTime": "2026-01-25",
                    "password": "p8q2r5s7"
                },
                {
                    "projectNumber": 58309,
                    "projectType": "化学工程",
                    "projectName": "绿色化工工艺开发",
                    "endTime": "2024-10-12",
                    "password": "t3u7v2w8"
                },
                {
                    "projectNumber": 74218,
                    "projectType": "心理学",
                    "projectName": "青少年心理健康干预",
                    "endTime": "2025-08-20",
                    "password": "x4y7z2a5"
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