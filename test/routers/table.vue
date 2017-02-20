<template>
<<<<<<< HEAD
    <i-button @click="changeFilter">改变filter</i-button>
    <span v-if="currentRow !== null">Current Row: {{currentRow.name}}</span>
    <Switch size="small" @on-change="switchCellEllipsis"></Switch> Ellipsis
    <i-table
      border
      :columns="columns6"
      :data="data5"
      :highlight-row="true"
      @on-current-change="onCurrentChange"
      @on-dblclick="onDblclick">
    </i-table>
    <br/>
    <i-table
      :columns="columns6"
      :data="[]">
    </i-table>
    <br/>
    <i-table
      :columns="columns6"
      size="small"
      :data="[]">
    </i-table>
    <br/>
    <i-table
      :columns="columns6"
      size="large"
      :data="data6">
    </i-table>
    <br/>
    No Prompt
    <i-table
      :columns="columns6"
      empty-text=""
      :data="[]">
    </i-table>
=======
    <i-table border :content="self" :columns="columns7" :data="data6"></i-table>
>>>>>>> 253
</template>
<script>
    export default {
        data () {
            return {
                self: this,
                columns7: [
                    {
                        title: '姓名',
                        key: 'name',
                        render (row, column, index) {
                            return `<Icon type="person"></Icon> <strong>${row.name}</strong>`;
                        }
                    },
                    {
                        title: '年龄',
                        key: 'age',
                        sortable: true,
                        sortMethod: function (a, b, type) {
                            if (type === 'asc') {
                                return a < b ? 1 : -1;
                            } else if (type === 'desc') {
                                return a > b ? 1 : -1;
                            }
                        }
                    },
                    {
                        title: '地址',
                        key: 'address'
                    },
                    {
                        title: '操作',
                        key: 'action',
                        width: 150,
                        align: 'center',
                        render (row, column, index) {
//                            return `<i-button type="primary" size="small" @click="show(${index})">查看</i-button> <i-button type="error" size="small" @click="remove(${index})">删除</i-button>`;
                            return `<Poptip width="250" confirm placement="left" title="您确认删除吗？" @on-ok="deleteProject(${index})">
                <i-button size="small" type="error">删除</i-button>
              </Poptip>`
                        }
                    }
                ],
<<<<<<< HEAD
                data5: [
                   {
                       name: '王小明',
                       age: 18,
                       address: '北京市朝阳区芍药居',
                       date: '2016-10-03',
                       longText: 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
                   },
                   {
                       name: '张小刚',
                       age: 25,
                       address: '北京市海淀区西二旗',
                       date: '2016-10-01',
                       longText: 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
                   },
                   {
                       name: '李小红',
                       age: 30,
                       address: '上海市浦东新区世纪大道',
                       date: '2016-10-02',
                       longText: 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
                   },
                   {
                       name: '周小伟',
                       age: 26,
                       address: '深圳市南山区深南大道',
                       date: '2016-10-04',
                       longText: 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
                   }
                ],
                data6: [],
                currentRow: null
            }
        },
        methods: {
            changeFilter () {
                this.columns6[2].filters = [
=======
                data6: [
>>>>>>> 253
                    {
                        name: '王小明',
                        age: 18,
                        address: '北京市朝阳区芍药居'
                    },
                    {
                        name: '张小刚',
                        age: 25,
                        address: '北京市海淀区西二旗'
                    },
                    {
                        name: '李小红',
                        age: 30,
                        address: '上海市浦东新区世纪大道'
                    },
                    {
                        name: '周小伟',
                        age: 26,
                        address: '深圳市南山区深南大道'
                    }
                ]
            }
        },
        methods: {
            show (index) {
                this.$Modal.info({
                    title: '用户信息',
                    content: `姓名：${this.data6[index].name}<br>年龄：${this.data6[index].age}<br>地址：${this.data6[index].address}`
                })
            },
            remove (index) {
                this.data6.splice(index, 1);
            }
        },
        ready () {
            setTimeout(() => {
                this.data6 = this.data5
            }, 1000)
        }
    }
</script>
