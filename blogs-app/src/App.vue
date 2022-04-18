<template>
  <div id="app">

    <add-blog/>  

  </div>
</template>


<script>
  import AddBlog from "./components/AddBlog.vue";

  export default {
    name: 'App',

    // props
    props : {

    },

    // components
    components : {
      'add-blog' : AddBlog
    },

    // data
    data() {
      return {

      }
    },

    // methods
    methods : {

    }

  }

</script>


<style>
  
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }

  body {
    margin : 0;
    padding: 1rem;
  }

  /* ---- Component Styles ---- */
    .form {
        display: flex;
        flex-direction: column;
        padding: 0 30vw;
    }

    .form * {
      margin: 0.5rem 0;
    }

    .form input {
        padding: 0.5rem;
    }

    .add-title {
        text-align: center;
    }

</style>
