<template>
    <div class="container mt-5">
      <div class="row">
        <div class="col-4 mx-auto">
          <app-comment></app-comment>
        </div>
      </div>
    </div>
</template>

<script>
  import Vue from 'vue'
  import BootstrapVue from 'bootstrap-vue'
  Vue.use(BootstrapVue)
  import 'bootstrap/dist/css/bootstrap.css'
  import 'bootstrap-vue/dist/bootstrap-vue.css'
  
  import Comment from './components/Comment.vue';

  export default {
      components: {
        AppComment: Comment,
      }
  }
</script>

<style>

</style>
