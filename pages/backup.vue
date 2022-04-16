<template>
  <div class="py-4">
    <div class="container">
      <div
        class="title border-bottom d-flex align-items-center justify-content-between py-2"
      >
        <h5>Task</h5>
        <div class="d-flex align-items-center">
          <button class="btn btn-outline-primary py-1 px-3 me-4" @click="shuffle">
          Shuffle!
</button>
          <div class="dropdown">
            <select v-model="category">
              <option value="Marketing">Marketing</option>
              <option value="Research">Research</option>
              <option value="Development">Product Development</option>
            </select>
          </div>
          <!--  <b-dropdown id="dropdown-1" text="Category" class="m-md-2">
    <b-dropdown-item
    v-for="(item,i) in resultCategory"
    :key="i"
    @click="cat = item"
    > {{item}} </b-dropdown-item>
  </b-dropdown>
</div>
-->
          &nbsp;&nbsp;
          <input
            type="text"
            class="form-control"
            placeholder="Search"
            v-model="searchQuery"
          />
          <span class="me-2">View </span>
          <button
            class="btn btn-outline-secondary py-1 px-3"
            @click="isGrid = !isGrid"
          >
            {{ isGrid ? "Grid" : "List" }}
          </button>
        </div>
      </div>
      <div class="list-task row">
        <transition-group name="tasks" tag="div" class="list-task row">
        <CardItem
         v-for="task in resultQuery"
          :key="task.id"
          :task="task"
          :isGrid="isGrid"
          :ok="ok"
        />
        </transition-group>
      </div>
    </div>
    
    <div>

      <div class="action py-2">
        <a
          href="#"
          class="add-button"
          v-if="!isCreating"
          @click="isCreating = !isCreating"
          >Add Task</a
        >
        <div class="add-card" v-else>
          <div class="card mb-2">
            <div class="card-body d-flex flex-column p-0">
              <form v-on:submit.prevent="handleSubmit">
              <input v-model="judul"
                class="form-control border-0 mb-2"
                placeholder="Title"
                type="text"
              />
              <label for="category">Category:</label>
              <select v-model="kategori" class="form-control border-0 mb-2" name="category" id="category">
              <option value="research">Research</option>
              <option value="project">Project</option>
              </select>
              <textarea v-model="deskripsi"
                class="form-control border-0 small"
                placeholder="Description"
                rows="3"
              ></textarea>
            </form>
            </div>
          </div>
          <div class="button-wrapper d-flex">
            <button class="btn btn-primary me-2" @click="addOne">Save</button>
            <button
              class="btn btn-outline-secondary"
              @click="isCreating = !isCreating"
            >
              Cancel
            </button>
            
          </div>
        </div>
      </div>
      <br />
      <br />
      <div v-if="ok == true">
        <button @click="ok = !ok">Hide All Hidden</button>
      </div>
      <div v-if="ok == false">
        <button @click="ok = !ok">Show All Hidden</button>
      </div>
      <p id="demo"></p>
    </div>
  </div>
</template>
<script>
import CardItem from "~/components/Card/CardItem.vue";

export default {
  components: {
    CardItem,
  },

  data() {
    return {
      ok: true,
      judul: '',
      kategori: '',
      deskripsi: '',

      task: [
        {
          id:1,
          title: 'Judul 1',
          category: 'Project',
          description: 'Ini adalah judul 1',
          isDone: false
        },
        {
          id:2,
          title: 'Judul 2',
          category: 'Riset',
          description: 'Ini adalah judul 2',
          isDone: false
        },
        {
          id:3,
          title: 'Judul 3',
          category: 'Proyek',
          description: 'Ini adalah judul 3',
          isDone: false,
        },
      ],
      searchQuery: "",
      category: "",
      isCreating: false,
      isGrid: false,
    };
  },

   computed: {
    resultQuery() {
      if (this.category) {
        return this.task.filter((item) => {
          return this.category
            .toLowerCase()
            .split(" ")
            .every((v) => item.category.toLowerCase().includes(v));
        });
      } else {
        console.log(this.task);
        return this.task;
      }
    },

    resultCategory() {
      let a = this.task
        .map((item) => item.category)
        .filter((value, index, self) => self.indexOf(value) === index);
      console.log(a);
      return a;
    },
  },

  methods: {
shuffle() {
this.task = _.shuffle(this.task)
}
},
addOne() {
      this.task.push({ title: this.judul, category: this.kategori, description: this.deskripsi, isDone: false });
      this.title = '';
      this.description = '';
},

};
</script>
<style>
#app .tasks-move {
transition: .4s;
}
.red {
  color: blue;
}
</style>
