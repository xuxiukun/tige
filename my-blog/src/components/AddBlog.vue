<template>
  <div class="add-blog">
   <h2>添加博客</h2>
   <form>
       <label>博客标题</label>
       <input type="text" v-model="blog.title">
       <label>博客内容</label>
       <textarea v-model="blog.content"></textarea>
       <div id="checkboxes">
           <input type="checkbox" value="Vue.js" v-model="blog.categories">
           <label>Vue.js</label>
           <input type="checkbox" value="Angular.js" v-model="blog.categories">
           <label>Angular.js</label>
           <input type="checkbox" value="React.js" v-model="blog.categories">
           <label>React.js</label>
           <input type="checkbox" value="Node.js" v-model="blog.categories">
           <label>Node.js</label>
       </div>
       <label>作者：</label>
       <select v-model="blog.author">
           <option v-for = "author in authors" >
               {{author}}
           </option>
       </select>
       <button v-on:click.prevent="post">添加博客</button>
   </form>
    <hr>
    <div id="preview">
        <h3>博客总览</h3>
        <p>博客标题：{{blog.title}}</p>
        <p>博客内容：</p>
        <p>{{blog.content}}</p>
        <p>博客分类：</p>
        <ul>
            <li v-for = "category in blog.categories">
                {{category}}
            </li>
        </ul>
        <p>作者：{{blog.author}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'add-blog',
  data () {
    return {
      blog:{
          title:"",
          content:"",
          categories:[],
          author:"",
        },
        authors:["Hemiah","Henry","Bucky"],

    }
  },
  methods:{
      post:function(){
          this.$http.post()
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
</style>
