<template>
<b-container>
    <p>
        <img src="../assets/logo.png">
    </p>
    <!-- <input type="text" v-model="msg"> -->
    <div>
        <b-input-group prepend="Task name" class="mt-3">
            <b-form-input v-model="msg"></b-form-input>
            <b-input-group-append>
                <b-button variant="info" v-on:click="add">Add</b-button>
            </b-input-group-append>
        </b-input-group>
    </div>
    <table class="table">
        <tr v-for="task in tasks" v-bind:key="task.summary">
            <td>
                {{ task.summary }}
            </td>
            <td>
                <button class="btn btn-primary">削除</button>
            </td>
        </tr>
    </table>
    <p>
        <router-link to="/page2">Go to page2</router-link>
    </p>
</b-container>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: "",
      tasks: []
    }
  },
  methods: {
    add() {
      this.tasks.push({ summary: this.msg });
      this.msg = "";
    },
    delete() {}
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
</style>
