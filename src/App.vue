<template>
    <div class="container" id="app">
        <SourceSelection v-on:sourceChanged="setSource"></SourceSelection>
        <Newslist v-bind:source="source"></Newslist>
    </div>
</template>

<script>
    import SourceSelection from './components/SourceSelection'
    import Newslist from './components/Newslist'

    export default {
        name: 'app',
        components: {
            SourceSelection,
            Newslist
        },
        data(){
           return {
               source: ""
           }
        },
        methods: {
            //自定义事件sourceChanged 调用,
            //子组件触发事件　this.$emit(sourceChanged,source)
            setSource : function (source) {
                this.source = source;
            }
        }

    }
</script>

<style>
    #app {
        padding-top: 20px;

    }
</style>
