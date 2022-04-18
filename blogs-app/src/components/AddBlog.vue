<template>
  <div id="add-blog">

    <!-- Title -->
    <h2 class="add-title">
        Add a new blog post..
    </h2>
    
    <!-- Create Blog Form -->
    <form action="" class="form">

        <!-- Input Fields -->
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
            required
        >
        </textarea>

        <!-- Check Boxes -->
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

        <!-- Date Select -->
        <h3>Publish Date:</h3>
        <select v-model="newBlog.publishDate">
            <option v-for="(date, i) in availDates" :key="i">
                {{date}}
            </option>
        </select>

        <input type="submit" v-on:click.prevent="saveBlog" class="submit">

    </form>

    <br>

    <div id="preview" v-show="submitted">
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
        <p>
            Date: {{newBlog.publishDate}}
        </p>
    </div>

  </div>
</template>


<script>
    import axios from 'axios';

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
                    genres : [],
                    publishDate : ""
                },

                availDates : ['May', 'June', 'July', 'August', 'September', 'October'],

                submitted : false

            }
        },

        // methods
        methods : {

            // create (CRUD)
            saveBlog() {
                axios.post('https://jsonplaceholder.typicode.com/posts', {
                    method : 'POST',
                    body : {
                        title : this.newBlog.title,
                        body : this.newBlog.content,
                        userId : 99
                    }
                }).then(response => { 
                    this.submitted = true
                    console.log(response)
                })
            }

        },

        // lifecycle hooks
        /*mounted() {
            axios.get('https://jsonplaceholder.typicode.com/posts')
                .then(response => console.log(response.data))
                // .then(response => console.log(response))
        }*/

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

    select {
        width: 20vw;
    }

    .submit {
        margin-left: 25vw;
        margin-right: 25vw;
    }

</style>
