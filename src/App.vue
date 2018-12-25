<template>
    <div id="app">
        <table-render></table-render>
        <table-render2></table-render2>
        <table-render3></table-render3>
    </div>
</template>

<script>
    import tableRender from './ivew/tableRender'
    import tableRender2 from './ivew/tableRender2'
    import tableRender3 from './ivew/tableRender3'

    export default {
        name: 'app',
        components: {
            tableRender,
            tableRender2,
            tableRender3
        }
    }
</script>

<style>
</style>
