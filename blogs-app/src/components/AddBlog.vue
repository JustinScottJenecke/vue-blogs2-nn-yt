<template>
  <div id="add-blog">

    <h2 class="add-title">
        Add a new blog post..
    </h2>
    <form action="" class="form">
        <label for="blog-title">Blog Title:</label>
        <input 
            v-model="newBlog.title"
            type="text" 
            name="blog-title" 
            required
        >
        <label for="blog-content">Blog Content:</label>        
        <textarea 
            v-model.lazy="newBlog.content"
            name="blog-content"
            cols="30" 
            rows="3"
        >
        </textarea>
    </form>
    <div>
        
    </div>

    <div id="preview">
        <h3>
            Preview Blog
        </h3>
        <p>
            Blog Title: {{newBlog.title}}
        </p>
        <p>
            Blog Content: {{newBlog.content}}
        </p>
    </div>

  </div>
</template>


<script>

  export default {
    name: 'AddBlog',

    // props
    props : {

    },

    // components
    components : {

    },

    // data
    data() {
      return {
        
        newBlog: {
            title : "",
            content : ""
        }

      }
    },

    // methods
    methods : {

    }

  }

</script>


<style>
  

</style>
