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
                <el-form-item label="用户名">
                  <el-input v-model="formInline.user" placeholder="请输入用户名"></el-input>
                </el-form-item>

                <el-form-item>
                  <el-button type="primary" @click="onSubmit">查询</el-button>
                </el-form-item>

                <el-form-item>
                  <el-button type="success" @click="onAddNewUser">添加用户</el-button>
                </el-form-item>

              </el-form>
              <el-table
                :data="tableData"
                style="width: 100%">
                <el-table-column
                  label="日期"
                  width="180">
                  <template slot-scope="scope">
                    <i class="el-icon-time"></i>
                    <span style="margin-left: 10px">{{ scope.row.date }}</span>
                  </template>
                </el-table-column>
                <el-table-column
                  label="姓名"
                  width="180">
                  <template slot-scope="scope">
                    <el-popover trigger="hover" placement="top">
                      <p>姓名: {{ scope.row.name }}</p>
                      <p>住址: {{ scope.row.address }}</p>
                      <div slot="reference" class="name-wrapper">
                        <el-tag size="medium">{{ scope.row.name }}</el-tag>
                      </div>
                    </el-popover>
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

              <el-dialog title="添加新用户" :visible.sync="dialogFormVisible">
                <el-form :model="form">
                  <el-form-item label="用户名" :label-width="formLabelWidth">
                    <el-input v-model="form.name" autocomplete="off"></el-input>
                  </el-form-item>
                  <el-form-item label="密码" :label-width="formLabelWidth">
                    <el-input v-model="form.password" autocomplete="off"></el-input>
                  </el-form-item>
                  <el-form-item label="确认密码" :label-width="formLabelWidth">
                    <el-input v-model="form.confirmpassword" autocomplete="off"></el-input>
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
          name: '',
          password: '',
          confirmpassword: '',
        },
        formInline: {
          user: '',
          region: ''
        },
         tableData: [{
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1519 弄'
        }, {
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1516 弄'
        }]
      }
    },
    methods: {
      onAddNewUser(){
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
                        <el-form-item label="用户名">
                            <el-input v-model="formInline.user" placeholder="请输入用户名" clearable></el-input>
                        </el-form-item>

                        <el-form-item>
                            <el-button type="primary" @click="onSubmit" icon="el-icon-search">查询</el-button>
                        </el-form-item>

                        <el-form-item>
                            <el-button type="success" @click="onAddNewUser" icon="el-icon-plus">添加用户</el-button>
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
                        :header-cell-style="{background:'#f5f7fa',color:'#606266'}"
                    >
                        <el-table-column
                            prop="date"
                            label="注册日期"
                            width="180"
                            align="center"
                        >
                            <template slot-scope="scope">
                                <i class="el-icon-time"></i>
                                <span style="margin-left: 10px">{{ scope.row.date }}</span>
                            </template>
                        </el-table-column>
                        
                        <el-table-column
                            prop="name"
                            label="用户名"
                            width="180"
                            align="center"
                        >
                            <template slot-scope="scope">
                                <el-popover trigger="hover" placement="top">
                                    <p>用户名: {{ scope.row.name }}</p>
                                    <p>住址: {{ scope.row.address }}</p>
                                    <div slot="reference" class="name-wrapper">
                                        <el-tag size="medium" type="primary">{{ scope.row.name }}</el-tag>
                                    </div>
                                </el-popover>
                            </template>
                        </el-table-column>
                        
                        <el-table-column
                            prop="address"
                            label="地址"
                            align="center"
                        >
                        </el-table-column>
                        
                        <el-table-column label="操作" width="220" align="center">
                            <template slot-scope="scope">
                                <el-button
                                    size="mini"
                                    @click="handleEdit(scope.$index, scope.row)"
                                    icon="el-icon-edit"
                                >编辑</el-button>
                                <el-button
                                    size="mini"
                                    type="danger"
                                    @click="handleDelete(scope.$index, scope.row)"
                                    icon="el-icon-delete"
                                >删除</el-button>
                            </template>
                        </el-table-column>
                    </el-table>

                    <!-- 分页 -->
                    <div style="margin-top: 20px; text-align: center">
                        <el-pagination
                            background
                            layout="prev, pager, next, sizes, total"
                            :total="1000"
                            :page-sizes="[10, 20, 30, 50]"
                            :page-size="10"
                            @size-change="handleSizeChange"
                            @current-change="handleCurrentChange"
                        >
                        </el-pagination>
                    </div>
                </el-card>

                <!-- 弹出添加用户框 -->
                <el-dialog title="添加新用户" :visible.sync="dialogFormVisible">
                <el-form :model="form">
                  <el-form-item label="用户名" :label-width="formLabelWidth">
                    <el-input v-model="form.name" autocomplete="off"></el-input>
                  </el-form-item>
                  <el-form-item label="密码" :label-width="formLabelWidth">
                    <el-input v-model="form.password" autocomplete="off"></el-input>
                  </el-form-item>
                  <el-form-item label="确认密码" :label-width="formLabelWidth">
                    <el-input v-model="form.confirmpassword" autocomplete="off"></el-input>
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
        dialogFormVisible: false,
        form: {
          name: '',
          password: '',
          confirmpassword: '',
        },
        formInline: {
          user: '',
          region: ''
        },
        tableData: [{
          date: '2016-05-02',
          name: 'admin',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-04',
          name: 'user01',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
          date: '2016-05-01',
          name: 'testuser',
          address: '上海市普陀区金沙江路 1519 弄'
        }, {
          date: '2016-05-03',
          name: 'demo',
          address: '上海市普陀区金沙江路 1516 弄'
        }]
      }
    },
    methods: {
      onAddNewUser() {
        this.form = {
          name: '',
          password: '',
          confirmpassword: ''
        };
        this.dialogFormVisible = true;
      },
      handleEdit(index, row) {
        console.log(index, row);
        this.$message.info(`准备编辑用户: ${row.name}`);
      },
      handleDelete(index, row) {
        console.log(index, row);
        this.$confirm(`确认删除用户 ${row.name} 吗?`, '提示', {
          confirmButtonText: '确定',
          cancelButtonText: '取消',
          type: 'warning'
        }).then(() => {
          this.$message.success('删除成功');
        }).catch(() => {
          this.$message.info('已取消删除');          
        });
      },
      handleConfirm() {
        if (!this.form.name || !this.form.password || !this.form.confirmpassword) {
          this.$message.warning('请填写完整信息');
          return;
        }
        
        if (this.form.password !== this.form.confirmpassword) {
          this.$message.error('两次输入的密码不一致');
          return;
        }
        
        // 这里应该调用API添加用户
        console.log('添加用户:', this.form);
        this.$message.success('用户添加成功');
        this.dialogFormVisible = false;
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

<style>
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
}
</style>
