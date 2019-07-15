<template>
  <div id="app">
     <input type=" " v-model="todo"></input>
     <button @click="add()">+</button>
     <br />
     <hr>
     <h2>进行中</h2>
      <ul>
        <li v-for="(item,key) in jinxinglist" v-if="item.checked">
          <input type="checkbox"> {{item.title}}------ <button @click= "del(key)">-</button>
        </li>
      </ul>
      <hr>
         <h2>已完成</h2>
      <ul>
        <li v-for="(item,key) in jinxinglist" v-if="!item.checked">
          <input type="checkbox"> {{item.title}}------ <button @click= "del(key)">-</button>
        </li>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      todo:"",
      jinxinglist:[
        {
          title:"录制moc",
          checked:"false"
        },
          {
          title:"录制demo",
          checked:"true"
        }
      ],
      wanchenglist:[]

    }
  },methods:{
      add(){
         this.list.push(this.todo);
         this.todo="";
      },
      del(key){
        this.list.splice(key,1);
      }
  }
}
</script>

<style>

</style>
