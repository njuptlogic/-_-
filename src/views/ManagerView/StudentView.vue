<template>
    <div class="container">
        <p style="display: flex;justify-content: end;padding: 0 20px;margin: 10px;">
            <el-button type="primary" @click="dialogFormVisible = true">新增学生</el-button>
        </p>
        <el-table :data="filterTableData" style="width: 100%">
            <el-table-column label="学号" prop="学号" />
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
        <el-dialog v-model="dialogFormVisible" title="添加学生" width="500" style="padding: 10px 30px;">
            <el-form>
                <el-form-item label="学号" :label-width="formLabelWidth">
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
                    "姓名": "张三",
                    "性别": "男",
                    "学号": 234567,
                    "专业": "计算机科学",
                    "账号": "zhangsan001",
                    "密码": "p@ssw0rd1"
                },
                {
                    "姓名": "李四",
                    "性别": "女",
                    "学号": 765432,
                    "专业": "英语",
                    "账号": "lisi888",
                    "密码": "abc12345"
                },
                {
                    "姓名": "王五",
                    "性别": "男",
                    "学号": 111222,
                    "专业": "物理学",
                    "账号": "wangwu123",
                    "密码": "qwerty78"
                },
                {
                    "姓名": "赵六",
                    "性别": "女",
                    "学号": 333444,
                    "专业": "生物学",
                    "账号": "zhaoliu66",
                    "密码": "54321zyx"
                },
                {
                    "姓名": "孙七",
                    "性别": "男",
                    "学号": 555666,
                    "专业": "历史学",
                    "账号": "sunqi777",
                    "密码": "789abcde"
                },
                {
                    "姓名": "周八",
                    "性别": "女",
                    "学号": 888999,
                    "专业": "化学",
                    "账号": "zhouba99",
                    "密码": "mnbvcxz1"
                },
                {
                    "姓名": "吴九",
                    "性别": "男",
                    "学号": 444555,
                    "专业": "数学",
                    "账号": "wujiu55",
                    "密码": "123qweas"
                },
                {
                    "姓名": "郑十",
                    "性别": "女",
                    "学号": 777888,
                    "专业": "工程学",
                    "账号": "zhengshi0",
                    "密码": "asdzxc12"
                },
                {
                    "姓名": "钱一",
                    "性别": "男",
                    "学号": 123789,
                    "专业": "艺术学",
                    "账号": "qianyi11",
                    "密码": "345rtyfg"
                },
                {
                    "姓名": "陈二",
                    "性别": "女",
                    "学号": 654321,
                    "专业": "音乐学",
                    "账号": "chener22",
                    "密码": "fgh7890"
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