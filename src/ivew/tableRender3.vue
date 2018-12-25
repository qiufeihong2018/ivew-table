<template>
    <div style="padding: 32px 64px">
        第三种方法:slot-scope插槽
        <Table border :columns="columns" :data="data" ref="table">
            <template slot-scope="props" slot="table">
                <Select>
                    <Option :value="props.name">
                        {{props.name}}
                    </Option>
                    <Option :value="props.age">
                        {{props.age}}
                    </Option>
                    <Option :value="props.address">
                        {{props.address}}
                    </Option>
                    <Option :value="props.province">
                        {{props.province}}
                    </Option>
                    <Option :value="props.city">
                        {{props.city}}
                    </Option>
                    <Option :value="props.zip">
                        {{props.zip}}
                    </Option>
                </Select>
            </template>
        </Table>
    </div>
</template>

<script>
    export default {
        name: "tableRender3",
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
                        // row�õ�һ���е�����
                        render: (h, {row}) => {
                            // ���ý���propֵ
                            return h('div', this.$refs.table.$scopedSlots.table({
                                name: row.name,
                                age: row.age,
                                address: row.address,
                                province: row.province,
                                city: row.city,
                                zip: row.zip
                            }))
                        }
                    }
                ],
                data: []
            }
        },
        mounted() {
            this.data = [
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
</script>
