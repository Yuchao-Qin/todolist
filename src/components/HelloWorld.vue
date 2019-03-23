<template>
  <div class="hello">
    <i-table :columns="columns1" :data="data1"></i-table>
      <i-input :value.sync="value" placeholder="姓名..." v-model="entryname.name" style="width: 300px"></i-input>
      <i-input :value.sync="value" placeholder="年龄..." v-model="entryname.age" style="width: 300px"></i-input>
      <i-input :value.sync="value" placeholder="地址..." v-model="entryname.address" style="width: 300px"></i-input>
      <i-button type="primary" @click="submit">提交</i-button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      entryname:{
        name:'',
        age:'',
        address:''
      },
      columns1: [
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
                  }
                ],
        data1: [
        ]
        }
      },
  methods: {
    submit () {
         this.data1.push({...this.entryname});
         this.entryname.name = '';
         this.entryname.address = '';
         this.entryname.age = '';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
