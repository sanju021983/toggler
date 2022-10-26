<template>
    <form>
        {{ name }} - {{heroName}}
        <div>
            <input type="text" :value="inputLine"/>
        </div>
    </form>
</template>
<script>
import {Options, Vue} from "vue-class-component";
export default{
    name:"Timer",
    props: ['name','heroName'],
    data(){
        return {
            inputLine: "sadfa"
        }
    },
    methods:{

    }
}
</script>
<style scoped lang="scss">

</style>
