<template>
  <div>
    <div v-if="errors.length">
      <p v-for="error in errors">{{ error }}</p>
    </div>
    <form class="simple-form" action="" method="post" v-on:submit.prevent="onSubmit">
      <p>りんご</p>
      <input v-model="message" placeholder="edit me">
      <p>write spell: {{ message }}</p>
      <button type="submit">submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Form',
  data () {
      return {
          message: '',
          errors: [],
      }
  },
  methods: {
      onSubmit:function (e) {
          this.errors = [];
          if (!this.message) {
              this.errors.push("ちゃんと入力しろし");
          } else {
              if(this.message == 'apple') {
                  this.errors.push("正解");
              } else {
                  this.errors.push("不正解");
                  this.errors.push("apple");
              }

          }
          e.preventDefault();
      }
  }
}
</script>
