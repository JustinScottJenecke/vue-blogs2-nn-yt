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

        <div id="blog-checkboxes">
            <span class="fieldset">            
                <label>Backend</label>
                <input type="checkbox" value="backend" name="" id="" v-model="newBlog.genres">
            </span>

            <span class="fieldset">
                <label>Frontend</label>
                <input type="checkbox" value="frontend" name="" id="" v-model="newBlog.genres">
            </span>

            <span class="fieldset">
                <label>Devops</label>
                <input type="checkbox" value="devops" name="" id="" v-model="newBlog.genres">
            </span>

            <span class="fieldset">            
                <label>Full-Stack</label>
                <input type="checkbox" value="full-stack" name="" id="" v-model="newBlog.genres">            
            </span>
        </div>

    </form>

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
        <p>
            Blog Genres:
        </p>
        <ul>
            <li v-for="(genre, i) in newBlog.genres" :key="i">
                {{genre}}
            </li>
        </ul>
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
            content : "",
            genres : []
        }

      }
    },

    // methods
    methods : {

    }

  }

</script>


<style scoped>
 
    #blog-checkboxes {
        display: flex;
        flex-direction: column;
    }

    .fieldset *{
        margin: 0rem 0.25rem;
    }

    #preview {
        border: solid 1px;
        padding: 1rem;

    }

    .form {
        border: solid 1px;
        padding: 1rem;
    }

</style>
