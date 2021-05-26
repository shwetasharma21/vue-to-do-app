<template>
  <div class="content">
    <div class="content-input">
      <input class="input" type="text" placeholder="Title" v-model="title" />
      <textarea
        class="desc-box input"
        placeholder="Description"
        v-model="description"
      />
      <label style="color:white;" for="date">Target Date</label>
      <input id="date" class="input" type="date" v-model="date" />
      <button class="btn input" v-on:click="createToDo">Create</button>
    </div>
    <div class="content-list">
      <h1 class="list-heading">To Do List</h1>
      <div class="item-area">
        <ul>
          <li v-for="item in toDoList" :key="item.id">
            <div class="list-item">
              <div class="item-head">
                <h3>{{ item.title }}</h3>
                <img
                  src="../assets/del_btn.svg"
                  alt="Delete"
                  v-on:click="delToDo(item.id)"
                />
              </div>
              <hr />
              <p>{{ item.description }}</p>
              <h4>{{ item.date }}</h4>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Content",
  data() {
    return {
      title: "",
      description: "",
      date: "",
      toDoList: [],
      count: 1,
    };
  },
  methods: {
    createToDo() {
      let { title, description, date, toDoList, count } = this;
      if (title.length === 0 || description.length === 0 || date.length === 0) {
        return alert("Input fields can't be empty");
      }
      const item = { id: count, title, description, date };
      toDoList.push(item);
      this.title = "";
      this.description = "";
      this.date = "";
      this.count++;
    },
    delToDo(id) {
      const item = this.toDoList.find((todo) => todo.id === id);
      const index = this.toDoList.indexOf(item);

      this.toDoList.splice(index, 1);
    },
  },
};
</script>

<style scoped>
.content {
  display: flex;
  flex: 1 1 auto;
  overflow: hidden;
}
.content-input {
  background-color: #393e46;
  width: 25rem;
  display: flex;
  flex-direction: column;
  padding: 1rem;
}
.content-list {
  background-color: white;
  flex: 1 1 auto;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}
.desc-box {
  height: 15rem;
  resize: none;
}
.input {
  padding: 0.5rem;
  margin-bottom: 0.5rem;
  border: none;
}
.btn {
  border: 1px solid white;
  cursor: pointer;
  width: 5rem;
  margin-left: auto;
  margin-right: auto;
}
.list-heading {
  background: #393e46;
  margin: 0;
  color: white;
}
.list-item {
  padding: 0.5rem;
  margin: 1rem;
  border: 1px solid black;
  border-radius: 1rem;
  display: flex;
  text-align: left;
  flex-direction: column;
  width: 80%;
  max-width: 50rem;
}
.item-head {
  display: flex;
  justify-content: space-between;
}
.item-area {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  overflow: scroll;
  overflow-x: hidden;
}
p {
  max-width: 50rem;
  word-break: break-all;
  margin: 0;
}
h3 {
  margin: 0;
}
h4 {
  padding: 0;
  text-align: right;
  margin: 0;
  font-weight: normal;
}
hr {
  width: 100%;
}
ul,
li {
  list-style-type: none;
}
</style>
