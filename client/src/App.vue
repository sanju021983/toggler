<template>
    <Timer :id="'timer_txt'" name="Diana" heroName="Wonder Women" />
    <Timer :id="'timer_txt'" name="Bruce" heroName="BatMan" />
    <Timer :id="'timer_txt'" name="Randi" />
    <WorkList/>
<!--    <form>-->
<!--        <input type="text" v-model="name"/>-->
<!--        <select name="students" v-model="selectedStudents" size="10" multiple>-->
<!--            <option v-for="(name, index) in students" :key="name" :value="name">{{index+1}} &ndash;&gt; {{name}}</option>-->
<!--        </select>-->
<!--    </form>-->
<!--    {{ name}}-->
<!--    <div v-html="channel" v-bind:id="'timer_txt2'"></div>-->
<!--    <button :disabled="isDisabled" @click="disableEnable" >Click Me</button>-->
<!--    <button @click="suffle" v-on:mouseover="show($event)" >Click Me</button>-->
<!--    <div :style="{-->
<!--        color:'red',-->
<!--        'font-weight':'bold',-->
<!--    }">{{ name }}</div>-->
<!--    <ul>-->
<!--        <li v-for="(name, index) in students" :key="name">{{index+1}} &ndash;&gt; {{name}}</li>-->
<!--    </ul>-->
<!--    <ul>-->
<!--        <li v-for="(name, index) in fullNames" :key="name.first">{{index+1}} &ndash;&gt; {{name.first}} {{name.last}}</li>-->
<!--    </ul>-->
<!--    <ul>-->
<!--        <template v-for="(value, name, index ) in myinfo" :key="name.first">-->
<!--            <li v-if="index%2==0">-->
<!--                <label>{{index+1}} &ndash;&gt; {{name}} {{value}}</label>-->
<!--                <input type="text" :value="value" :id="name" :name="name" @change="alertThis($event)"/>-->
<!--            </li>-->
<!--        </template>-->
<!--    </ul>-->
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view/>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
<script>
// import Timer from "@/components/Timer";
import Timer from "./components/Timer";
import _ from "lodash";
import WorkList from "@/components/WorkList";
export default {
    name:"App",
    data() {
        return {
            name: "Vipan Kumar",
            channel: '<b>code</b>',
            isDisabled: false,
            students: ["vipan", "kumar",'karan'],
            selectedStudents:["vipan", "kumar",'karan'],
            fullNames: [
                { first: "karan", last: "Kumar"},
                { first: "karan", last: "Kumar"},
                { first: "Diana",last: "Princes"}
            ],
            myinfo:{
                name: "Vipan Kumar",
                age: "918",
                address: "Address"
            }
        }
    },
    methods: {
        alertThis(event){
            console.log(event)
          alert('aaa')
        },
        disableEnable(){
          this.isDisabled = !this.isDisabled;
        },
        show(event){
            console.log(event)
        },
        suffle(){
            this.students = _.shuffle(this.students);
            this.fullNames = _.shuffle(this.fullNames);
            this.myinfo = _.shuffle(this.myinfo);
        }
    },
    components: {
        Timer,
        WorkList
    }
}
</script>
