<template>
  <v-card>
      <v-flex xs12 sm10>
        <v-tree url="/item/category/list"

                :isEdit="isEdit"
                @handleAdd="handleAdd"
                @handleEdit="handleEdit"
                @handleDelete="handleDelete"
                @handleClick="handleClick"
        />
      </v-flex>
  </v-card>
</template>
<!--上面的标签是怎么请求到  api.leyou.com 这路径的 , 从 http.js找到 config.js , 已经前端报的  No 'Access-Control-Allow-Origin 跨域问题-->
<script>
  import {treeData} from "../../mockDB";
  //下面treedata:[],由于数据模型和数据内容一样,可以省略,写成 treedata
  export default {
    name: "category",
    data() {
      return {
        isEdit:true,
        treeData
      }
    },
    methods: {
      handleAdd(node) {
        console.log("add .... ");
        console.log(node);
      },
      handleEdit(id, name) {
        console.log("edit... id: " + id + ", name: " + name)
      },
      handleDelete(id) {
        console.log("delete ... " + id)
      },
      handleClick(node) {
        console.log(node)
      }
    }
  };
</script>

<style scoped>

</style>
