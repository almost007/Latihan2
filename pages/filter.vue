<template>
 <div>
   <select
    id="category"
    name="category"
    v-model="selected">
     <option value="0">categories</option>
     <option value="1">1</option>
     <option value="2">2</option>
   </select>
   <services-task :task="services.task" /> 
 </div>
</template>
<script>


import CardItem from "~/components/Card/CardItem.vue"

export default {
  components: {
CardItem
},

  data() {
    return {
         services: {
      task: [
        {
          title: "Validasi Masalah",
          category: "Research",
          description: "Lakukan validasi masalah kepada target user minimal 30 untuk kategori B2C dan 5 untuk kategori B2B.",
          isDone: false,
        },
        {
          title: "Membuat MVP",
          category: "Product Development",
          description: "Buat MVP sederhana berdasarkan permasalahan user",
          isDone: false,
        },
        {
          title: "Testing MVP",
          category: "Research",
          description: "Lakukan pengujian MVP kepada user dan minta feedback mereka.",
          isDone: false,
        },
      ]},
      searchQuery: '',
      isCreating: false,
      isGrid: false,
    };
  },

  methods: {
    PilihKategori: function() {
        alert('ok');
    }
},

  computed: {
      filtered(){
    if (this.selected === null) return this.services.list
    return this.services.task.filter(s => s.category === this.selected)
  },

resultQuery() {
if (this.searchQuery) {
return this.task.filter((item) => {
return this.searchQuery
.toLowerCase()
.split(" ")
.every((v) => item.title.toLowerCase().includes(v));
});
} else {
console.log(this.task);
return this.task
}
},
CekKategori(){
if(category.task=="Research") {
alert("Research Dipilih");
}
if(category.task=="Product Development") {
alert("Product Development Dipilih");
}
else {
alert("Semua dipilih!!");
console.log(this.task);
return this.task
}




}

},





};



</script>
<style>
.red {
  color: blue;
}
</style>
