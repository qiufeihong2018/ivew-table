<template>
    <div style="padding: 32px 64px">
        第一种方法:纯render渲染
        <Table border stripe :columns="columns" :data="data"></Table>
    </div>
</template>

<script>
    export default {
        name: "tableRender",
        data() {
            return {
                columns: [
                    {
                        title: '姓名',
                        key: 'name'
                    },
                    {
                        title: '年龄',
                        key: 'age'
                    },
                    {
                        title: '地址',
                        key: 'address'
                    },
                    {
                        title: '省份',
                        key: 'province'
                    },
                    {
                        title: '城市',
                        key: 'city'
                    },
                    {
                        title: 'zip',
                        key: 'zip'
                    },
                    {
                        title: '操作',
                        // row拿到一整行的数据
                        render: (h, {row}) => {
                            // 不用接受prop值
                            return h('Select', {}, [
                                h('Option', {
                                    props: {
                                        value: row.name
                                    }
                                }, row.name),
                                h('Option', {
                                    props: {
                                        value: row.age
                                    }
                                }, row.age),
                                h('Option', {
                                    props: {
                                        value: row.address
                                    }
                                }, row.address),
                                h('Option', {
                                    props: {
                                        value: row.province
                                    }
                                }, row.province),
                                h('Option', {
                                    props: {
                                        value: row.city
                                    }
                                }, row.city),
                                h('Option', {
                                    props: {
                                        value: row.zip
                                    }
                                }, row.zip)
                            ])
                        }
                    }
                ],
                data: [
                    {
                        name: 'John Brown',
                        age: 18,
                        address: 'New York No. 1 Lake Park',
                        province: 'America',
                        city: 'New York',
                        zip: 100000
                    },
                    {
                        name: 'Jim Green',
                        age: 24,
                        address: 'Washington, D.C. No. 1 Lake Park',
                        province: 'America',
                        city: 'Washington, D.C.',
                        zip: 100000
                    },
                    {
                        name: 'Joe Black',
                        age: 30,
                        address: 'Sydney No. 1 Lake Park',
                        province: 'Australian',
                        city: 'Sydney',
                        zip: 100000
                    },
                    {
                        name: 'Jon Snow',
                        age: 26,
                        address: 'Ottawa No. 2 Lake Park',
                        province: 'Canada',
                        city: 'Ottawa',
                        zip: 100000
                    }
                ]
            }
        }
    }
</script>
