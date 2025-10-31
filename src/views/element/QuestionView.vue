<!-- <template>
    <el-container>
        <el-header style="font-size: 40px; background-color: rgb(238, 241, 246)">Quiz后台管理</el-header>
        <el-container>
            <el-aside width="200px" style="background-color: rgb(238, 241, 246)">
                <el-menu :default-openeds="['1']">
                <el-submenu index="1">
                    <template slot="title">管理选项</template>
                    <el-menu-item-group>
                    <el-menu-item index="1-1"><router-link to="/user">用户管理</router-link></el-menu-item>
                    <el-menu-item index="1-2"><router-link to="/question">题目管理</router-link></el-menu-item>
                    </el-menu-item-group>
                   
                </el-submenu>

                </el-menu>
            </el-aside>

            <el-main>
              <el-form :inline="true" :model="formInline" class="demo-form-inline">
                <el-form-item label="题目">
                  <el-input v-model="formInline.user" placeholder="请输入题目关键词"></el-input>
                </el-form-item>
   
                <el-form-item>
                  <el-button type="primary" @click="onSubmit">查询</el-button>
                </el-form-item>

                <el-form-item>
                  <el-button type="success" @click="onAddNewQuestion">添加题目</el-button>
                </el-form-item>

              </el-form>
              <el-table
                :data="tableData"
                style="width: 100%">
                <el-table-column label="序号" width="50">
                  <template slot-scope="scope">
                   <span style="margin-left: 10px">{{ scope.row.id }}</span>
                  </template>
                </el-table-column>

                <el-table-column label="题目" width="250">
                  <template slot-scope="scope">
                      <div slot="reference" class="name-wrapper">
                        <span style="margin-left: 10px">{{ scope.row.question }}</span>
                      </div>
                  </template>
                </el-table-column>

                <el-table-column label="选项" width="260">
                  <template slot-scope="scope">
                      <span style="margin-left: 10px">{{ scope.row.options }}</span>
                    </template>
                </el-table-column>

                <el-table-column label="答案" width="180">
                  <template slot-scope="scope">
                      <span style="margin-left: 10px">{{ scope.row.answer }}</span>
                    </template>
                </el-table-column>

                <el-table-column label="操作">
                  <template slot-scope="scope">
                    <el-button
                      size="mini"
                      @click="handleEdit(scope.$index, scope.row)">编辑</el-button>
                    <el-button
                      size="mini"
                      type="danger"
                      @click="handleDelete(scope.$index, scope.row)">删除</el-button>
                  </template>
                </el-table-column>
              </el-table>

              <br />
              <el-pagination
                background
                layout="prev, pager, next"
                :total="1000">
              </el-pagination>

              <el-dialog title="添加新题目" :visible.sync="dialogFormVisible">
                <el-form :model="form">
                  <el-form-item label="题目" :label-width="formLabelWidth">
                    <el-input v-model="form.qiestion" autocomplete="off"></el-input>
                  </el-form-item>
                  <el-form-item label="选项a" :label-width="formLabelWidth">
                    <el-input v-model="form.optiona" autocomplete="off"></el-input>
                  </el-form-item>
                  <el-form-item label="选项b" :label-width="formLabelWidth">
                    <el-input v-model="form.optionb" autocomplete="off"></el-input>
                  </el-form-item>
                  <el-form-item label="选项c" :label-width="formLabelWidth">
                    <el-input v-model="form.optionc" autocomplete="off"></el-input>
                  </el-form-item>
                  <el-form-item label="选项d" :label-width="formLabelWidth">
                    <el-input v-model="form.optiond" autocomplete="off"></el-input>
                  </el-form-item>
                  <el-form-item label="答案" :label-width="formLabelWidth">
                    <el-input v-model="form.answer" autocomplete="off"></el-input>
                  </el-form-item>
                </el-form>
                <div slot="footer" class="dialog-footer">
                  <el-button @click="dialogFormVisible = false">取 消</el-button>
                  <el-button type="primary" @click="dialogFormVisible = false">确 定</el-button>
                </div>
              </el-dialog>
            </el-main>
        </el-container>
    </el-container>
</template>

<script>
export default {
    data() {
      return {
        dialogFormVisible:false,
          form: {
          question: '',
          optiona: '',
          optionb: '',
          optionc: '',
          optiond: '',
          answer:'',
        },
        formInline: {
          user: '',
          region: ''
        },
         tableData: [{
          id:"1",
          question:"法国的首都是哪个城市",
          options:"巴黎，巴黎，巴黎，巴黎",
          answer:"巴黎",
        }, {
          id:"2",
          question:"法国的首都是哪个城市",
          options:"巴黎，巴黎，巴黎，巴黎",
          answer:"巴黎",
        }, {
           id:"3",
          question:"法国的首都是哪个城市",
          options:"巴黎，巴黎，巴黎，巴黎",
          answer:"巴黎",
        }, {
           id:"4",
          question:"法国的首都是哪个城市",
          options:"巴黎，巴黎，巴黎，巴黎",
          answer:"巴黎",
        }]
      }
    },
    methods: {
      onAddNewQuestion(){
        this.dialogFormVisible=true;
      },
      onSubmit() {
        console.log('submit!');
      },
       handleEdit(index, row) {
        console.log(index, row);
      },
      handleDelete(index, row) {
        console.log(index, row);
      }
    }
  }
</script>

<style>

</style>
 -->
<template>
    <el-container style="height: 100vh">
        <el-header style="font-size: 24px; background-color: #409EFF; color: white; display: flex; align-items: center; box-shadow: 0 2px 10px rgba(0,0,0,0.1)">
            <i class="el-icon-s-platform" style="margin-right: 10px"></i>
            <span>Quiz 后台管理系统</span>
        </el-header>
        
        <el-container>
            <el-aside width="220px" style="background-color: #304156; height: calc(100vh - 60px)">
                <el-menu 
                    :default-openeds="['1']" 
                    background-color="#304156"
                    text-color="#bfcbd9"
                    active-text-color="#409EFF"
                    router
                >
                    <el-submenu index="1">
                        <template slot="title">
                            <i class="el-icon-s-management"></i>
                            <span>系统管理</span>
                        </template>
                        <el-menu-item-group>
                            <el-menu-item index="/user">
                                <i class="el-icon-user"></i>
                                用户管理
                            </el-menu-item>
                            <el-menu-item index="/question">
                                <i class="el-icon-edit-outline"></i>
                                题目管理
                            </el-menu-item>
                        </el-menu-item-group>
                    </el-submenu>
                </el-menu>
            </el-aside>

            <el-main style="background-color: #f0f2f5; padding: 20px">
                <!-- 顶部的查询表单 -->
                <el-card shadow="hover" style="margin-bottom: 20px">
                    <el-form :inline="true" :model="formInline" class="demo-form-inline">
                        <el-form-item label="题目关键词">
                            <el-input 
                                v-model="formInline.keyword" 
                                placeholder="请输入题目关键词" 
                                clearable
                                prefix-icon="el-icon-search"
                                style="width: 300px"
                            ></el-input>
                        </el-form-item>

                        <el-form-item>
                            <el-button type="primary" @click="onSubmit" icon="el-icon-search">查询</el-button>
                        </el-form-item>

                        <el-form-item>
                            <el-button type="success" @click="onAddNewQuestion" icon="el-icon-plus">添加题目</el-button>
                        </el-form-item>
                    </el-form>
                </el-card>

                <!-- 表格展示 -->
                <el-card shadow="hover">
                    <el-table
                        :data="tableData"
                        style="width: 100%"
                        stripe
                        border
                        :header-cell-style="{background:'#f5f7fa',color:'#606266', fontWeight: '600'}"
                    >
                        <el-table-column
                            prop="id"
                            label="序号"
                            width="80"
                            align="center"
                        >
                            <template slot-scope="scope">
                                <el-tag type="info">{{ scope.row.id }}</el-tag>
                            </template>
                        </el-table-column>
                        
                        <el-table-column
                            prop="question"
                            label="题目"
                            min-width="300"
                            align="center"
                        >
                            <template slot-scope="scope">
                                <div class="question-content">
                                    <span>{{ scope.row.question }}</span>
                                </div>
                            </template>
                        </el-table-column>
                        
                        <el-table-column
                            label="选项"
                            min-width="350"
                            align="center"
                        >
                            <template slot-scope="scope">
                                <div class="options-list">
                                    <div v-for="(option, index) in scope.row.options" :key="index" class="option-item">
                                        <span class="option-label">{{ String.fromCharCode(65 + index) }}.</span>
                                        <span>{{ option }}</span>
                                    </div>
                                </div>
                            </template>
                        </el-table-column>
                        
                        <el-table-column
                            prop="answer"
                            label="答案"
                            width="120"
                            align="center"
                        >
                            <template slot-scope="scope">
                                <el-tag type="success" effect="dark">{{ scope.row.answer }}</el-tag>
                            </template>
                        </el-table-column>
                        
                        <el-table-column label="操作" width="200" align="center">
                            <template slot-scope="scope">
                                <el-button
                                    size="mini"
                                    type="primary"
                                    @click="handleEdit(scope.$index, scope.row)"
                                    icon="el-icon-edit"
                                    plain
                                >编辑</el-button>
                                <el-button
                                    size="mini"
                                    type="danger"
                                    @click="handleDelete(scope.$index, scope.row)"
                                    icon="el-icon-delete"
                                    plain
                                >删除</el-button>
                            </template>
                        </el-table-column>
                    </el-table>

                    <!-- 分页 -->
                    <div style="margin-top: 20px; text-align: center">
                        <el-pagination
                            background
                            layout="prev, pager, next, sizes, total"
                            :total="400"
                            :page-sizes="[10, 20, 30, 50]"
                            :page-size="10"
                            @size-change="handleSizeChange"
                            @current-change="handleCurrentChange"
                        >
                        </el-pagination>
                    </div>
                </el-card>

                <!-- 弹出添加题目框 -->
                <el-dialog 
                    title="添加新题目" 
                    :visible.sync="dialogFormVisible"
                    width="600px"
                    :close-on-click-modal="false"
                >
                    <el-form :model="form" label-width="80px" :rules="rules" ref="questionForm">
                        <el-form-item label="题目" prop="question">
                            <el-input 
                                v-model="form.question" 
                                autocomplete="off" 
                                placeholder="请输入题目内容"
                                type="textarea"
                                :rows="3"
                            ></el-input>
                        </el-form-item>
                        
                        <el-form-item label="选项" required>
                            <div class="options-container">
                                <el-form-item 
                                    v-for="(option, index) in form.options" 
                                    :key="index" 
                                    :prop="'options.' + index"
                                    :rules="{ required: true, message: '选项不能为空', trigger: 'blur' }"
                                    class="option-item-form"
                                >
                                    <el-input 
                                        v-model="form.options[index]"
                                        :placeholder="`选项 ${String.fromCharCode(65 + index)}`"
                                        style="margin-bottom: 10px"
                                    >
                                        <template slot="prepend">{{ String.fromCharCode(65 + index) }}.</template>
                                    </el-input>
                                </el-form-item>
                            </div>
                        </el-form-item>
                        
                        <el-form-item label="答案" prop="answer">
                            <el-select v-model="form.answer" placeholder="请选择正确答案" style="width: 100%">
                                <el-option 
                                    v-for="(option, index) in form.options" 
                                    :key="index"
                                    :label="`${String.fromCharCode(65 + index)}. ${option}`"
                                    :value="String.fromCharCode(65 + index)"
                                ></el-option>
                            </el-select>
                        </el-form-item>
                    </el-form>
                    <div slot="footer" class="dialog-footer">
                        <el-button @click="dialogFormVisible = false" icon="el-icon-close">取 消</el-button>
                        <el-button type="primary" @click="handleConfirm" icon="el-icon-check">确 定</el-button>
                    </div>
                </el-dialog>
            </el-main>
        </el-container>
    </el-container>
</template>

<script>
export default {
    data() {
      return {
        dialogFormVisible: false,
        form: {
          question: '',
          options: ['', '', '', ''],
          answer: ''
        },
        rules: {
          question: [
            { required: true, message: '请输入题目内容', trigger: 'blur' }
          ],
          answer: [
            { required: true, message: '请选择正确答案', trigger: 'change' }
          ]
        },
        formInline: {
          keyword: ''
        },
        tableData: [
          {
            id: "1",
            question: "法国的首都是哪个城市？",
            options: ["巴黎", "伦敦", "柏林", "马德里"],
            answer: "A"
          }, 
          {
            id: "2",
            question: "以下哪个不是编程语言？",
            options: ["Python", "Java", "HTML", "C++"],
            answer: "C"
          }, 
          {
            id: "3",
            question: "中国的首都是？",
            options: ["上海", "北京", "广州", "深圳"],
            answer: "B"
          }
        ]
      }
    },
    methods: {
      onAddNewQuestion() {
        this.form = {
          question: '',
          options: ['', '', '', ''],
          answer: ''
        };
        this.dialogFormVisible = true;
        this.$nextTick(() => {
          this.$refs.questionForm.clearValidate();
        });
      },
      onSubmit() {
        this.$message.success('查询功能待实现');
      },
      handleEdit(index, row) {
        this.$message.info(`准备编辑题目: ${row.question}`);
        // 这里可以打开编辑对话框，填充数据
      },
      handleDelete(index, row) {
        this.$confirm(`确认删除题目 "${row.question}" 吗?`, '提示', {
          confirmButtonText: '确定',
          cancelButtonText: '取消',
          type: 'warning'
        }).then(() => {
          this.tableData.splice(index, 1);
          this.$message.success('删除成功');
        }).catch(() => {
          this.$message.info('已取消删除');          
        });
      },
      handleConfirm() {
        this.$refs.questionForm.validate((valid) => {
          if (valid) {
            // 验证选项是否都填写了
            const emptyOption = this.form.options.some(option => !option.trim());
            if (emptyOption) {
              this.$message.warning('请填写所有选项');
              return;
            }
            
            // 这里应该调用API添加题目
            console.log('添加题目:', this.form);
            this.$message.success('题目添加成功');
            this.dialogFormVisible = false;
          } else {
            this.$message.warning('请填写完整信息');
            return false;
          }
        });
      },
      handleSizeChange(val) {
        console.log(`每页 ${val} 条`);
      },
      handleCurrentChange(val) {
        console.log(`当前页: ${val}`);
      }
    }
  }
</script>

<style scoped>
.el-header {
    padding: 0 20px;
}

.el-aside {
    transition: width 0.3s;
}

.el-menu {
    border-right: none;
}

.el-main {
    padding: 0;
}

.el-card {
    border-radius: 4px;
}

.el-card__header {
    padding: 15px 20px;
    border-bottom: 1px solid #ebeef5;
    box-sizing: border-box;
}

.el-table {
    margin-bottom: 20px;
}

.el-table th {
    font-weight: 600;
}

.el-pagination {
    margin-top: 20px;
    text-align: center;
}

.dialog-footer {
    text-align: center;
}

.question-content {
    text-align: left;
    padding: 8px 0;
}

.options-list {
    text-align: left;
}

.option-item {
    padding: 2px 0;
    display: flex;
    align-items: center;
}

.option-label {
    font-weight: bold;
    margin-right: 8px;
    color: #409EFF;
}

.options-container {
    border: 1px solid #e4e7ed;
    border-radius: 4px;
    padding: 15px;
    background-color: #fafafa;
}

.option-item-form {
    margin-bottom: 0;
}

/* 响应式调整 */
@media screen and (max-width: 768px) {
    .el-aside {
        width: 64px !important;
    }
    
    .el-menu-item span, .el-submenu__title span {
        display: none;
    }
    
    .el-submenu__icon-arrow {
        display: none;
    }
    
    .el-dialog {
        width: 95% !important;
    }
}
</style>