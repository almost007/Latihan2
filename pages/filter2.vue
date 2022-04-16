<template>

  <div>
    <pre>{{ task }}</pre>
    
  <div class="action py-2">
        <a
          href="#"
          class="add-button"
          v-if="!isCreating"
          @click="isCreating = !isCreating"
          >Add Task</a
        >
        <div class="add-card" v-else>
          <form v-on:submit.prevent>
          <div class="card mb-2">
            <div class="card-body d-flex flex-column p-0">
              
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
          </form>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isCreating: false,
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
    }
  },
  methods: {
    addOne() {
      this.task.push({ title: this.judul, category: this.kategori, description: this.deskripsi, isDone: false })
    },
  },
}
</script>