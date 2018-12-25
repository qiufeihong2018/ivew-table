<template>
    <Select>
        <Option :value="row.name">{{row.name}}</Option>
        <Option :value="row.age">{{row.age}}</Option>
        <Option :value="row.address">{{row.address}}</Option>
        <Option :value="row.province">{{row.province}}</Option>
        <Option :value="row.city">{{row.city}}</Option>
        <Option :value="row.zip">{{row.zip}}</Option>
    </Select>
</template>

<script>
    export default {
        name: "select",
        props: {
            row: Object
        }
    }
</script>