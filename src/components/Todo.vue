<template>
  <div class="container">
    <div class="form-container">
      <form action="#">
        <input type="text" v-model="newTodo" placeholder="enter your to do" />
        <button type="button" @click="addTask()">+</button>
      </form>
    </div>

    <div class="sub-container">
      <div class="btn-cover">
        <button class="btn" @click.prevent="deleteAll()">clear All</button>
        <button class="btn" @click.prevent="deleteTask()">clear All</button>
      </div>
      <div>
        <ul class="pending">
          <li v-for="(task, index) in tasks" :key="index">
            <span v-text="task.name"> </span>
            <button class="clear" @click="deleteTask(index)"></button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ToDo",
  data() {
    return {
      tasks: ["html", "css", "js"],
      task: "",
    };
  },
  methods: {
    addTask() {
      this.tasks.push({
        name: this.task,
      });
      localStorage.setItem("tasks", JSON.stringify(this.tasks));
      this.task = "";
      if (this.task == "") return;
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    },
    deleteAll() {
      this.task = [];
    },
  },
};
</script>

<style scoped>
.form-container {
  width: 80%;
  position: relative;
}

form {
  width: 86%;
  margin: 0 auto;
  height: 55px;
  margin-top: 15px;
  display: flex;
  justify-content: center;
  align-items: center;
}

form input[type="text"] {
  width: 100%;
  border-radius: 3px;
  border: 1px solid #0083da;
  color: #0083da;
  padding: 10px;
  font-size: 1.2em;
  outline: none;
}

form button {
  margin-left: 15px;
  border: 0;
  background-color: #0099ff;
  color: #ffffff;
  padding: 0 20px;
  border-radius: 3px;
  font-size: 2.4em;
  cursor: pointer;
  outline: none;
  transition: background-color 0.2s ease;
}

form button:hover {
  background-color: #0099ffed;
}

.btn-cover {
  text-align: center;
  margin: 25px 0 -10px;
}

.btn-cover .btn {
  border: none;
  outline: none;
  padding: 4px 8px;
  display: inline-block;
  border-radius: 2px;
  background-color: #0099ff21;
  color: #0083dad5;
  cursor: pointer;
  font-family: "Pacifico", cursive;
  margin: 0 10px 0 0;
  box-shadow: 2px 0px 3px 1px #0099ff21;
  transition: background-color 0.3s ease, box-shadow 0.3s ease;
}
.btn-cover .btn:hover {
  box-shadow: 2px 2px 5px 2px #0099ff21;
}

ul {
  list-style: none;
  padding: 0;
}

ul li {
  position: relative;
  padding: 13px;
  margin: 0 13px 8px;
  font-weight: 600;
  border-radius: 5px;
  background-color: #0099ff08;
  box-shadow: 2px 0px 3px 1px rgba(236, 240, 241, 0.6);
  cursor: pointer;
  user-select: none;
  transition: box-shadow 0.5s ease;
}

ul li:hover {
  box-shadow: 2px 2px 5px 2px rgb(214, 216, 216);
}
</style>
