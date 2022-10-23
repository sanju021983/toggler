<template>
    <form>
        <div>
            <input type="text"/>
        </div>
    </form>
</template>
<script lang="ts">
import {Options, Vue} from "vue-class-component";
export default class Timer extends Vue{
    data(){
        return {
            inputLine: ""
        }
    }
}
</script>
<style scoped lang="scss">

</style>
