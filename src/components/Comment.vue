<template>
<div class="app">
  <div class="row">
    <form class="form">
      <input v-model="name" class="comment__input" type="text" placeholder="Nome">
      <input v-model="email" class="comment__input" type="email" placeholder="Email *">
      <textarea v-model="comment" class="comment__text comment__input" rows="10" placeholder="Comentário *" required></textarea>
      <button @click="add_comments" class="comment__btn" type="button">ADICIONAR COMENTÁRIO</button>
    </form>
  </div>

<div class="list">
    <div v-for="(comment, i) in comments" :key="i" class="comment__user-wrapper">
      <div class="photo">
         <img src="../assets/pf.png">
      </div>
      <div class="info">
        <div class="name">{{ comment.name }} - Postado às</div>
        <div class="comment__user-text">
          <p> {{ comment.comment }}</p>
        </div>
      </div>
    </div>
  </div>
</div>

</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      name: "",
      email: "",
      comment: "",
      comments: []
    };
  },
  methods: {
    add_comments() {
      this.comments.unshift({ name: this.name, comment: this.comment });
      this.name = "";
      this.email = "";
      this.coment = "";
    }
  }
};
</script>

<style lang="scss">
.comments {
    margin: 30px 200px 0;

    .block-title {
    padding: 25px 0 15px;
    font-family: 'Montserrat';
    font-size: 25px;
    line-height: 1.2;
    text-transform: uppercase;
    border-bottom: 1px solid 
    #e1e1e1;
    margin: 0 0 20px;
    text-align: start;
  }

  .block-description {
    font-family: 'Montserrat';
    font-size: 12px;
    margin: 0 0 40px;
    text-align: start;
  }
}

.form {
  background:#f7f7f7;
  display: flex;
  padding: 20px 15px;
  flex-wrap: wrap;
  margin: 0 0 20px;
  border-radius: 5px;

  p {
    width: 100%;
    padding: 0 5px;
    font-size: 12px;
    color:
    #999;
    margin: 0 0 5px;
  }

  input {
    width: calc(50% - 10px);
    padding: 15px;
    font-family: sans-serif;
    font-size: 12px;
    border: 0;
    margin: 0 5px 10px;
    border-radius: 5px;
  }

  textarea {
    width: calc(75% - 10px);
    height: 45px;
    padding: 15px;
    font-family: sans-serif;
    font-size: 12px;
    border: 0;
    margin: 0 5px;
    border-radius: 5px;
  }

  button {
    background:#333;
    flex-grow: 1;
    font-family: sans-serif;
    font-size: 14px;
    font-weight: bold;
    color:
    #fff;
    text-align: center;
    text-transform: uppercase;
    border: 0;
    margin: 0 5px;
    border-radius: 5px;
    cursor: pointer;
  }
}

.list {
  text-align: start;

  .item {
    display: flex;
    padding: 0 0 25px;
    border-bottom: 1px solid#eee;
    margin: 0 0 25px;

    .photo {
      margin: 0 20px 0 0;
    }

    .info p {
      font-size: 12px;
      color:#666;
      margin: 0;
    }

    .info a {
      font-size: 10px;
      font-weight: bold;
      color:#000;
      text-transform: uppercase;
    }
  }
}
  

</style>