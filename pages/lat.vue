<!--<div <template>
<div class="py-4">
<div class="container">
<div class="title border-bottom">
<h5 class= "blue">Task</h5>
</div>
<div class="list-task">
<div class="item-task d-flex align-items-center border-bottom pt-3 pb-4">
<input type="checkbox" name="status" id="task" class="me-2">
<div class="title-task">Tugas 1</div>
</div>
</div>
<div class="action py-2">
<a href="#" class="add-button">Add Task</a>
</div>
<button v-bind:disabled="isButtonDisabled">Button</button>
{{msg}}
{{ number + 1 }}
{{ ok ? 'YES' : 'NO' }}
<div v-bind:id="'list-' + id">Saya Baru Makan</div>
<p v-if="seen">Now you see me</p>
<p v-if="!seen">seen is {{seen}}</p>
<a v-bind:href="url"> ... </a>,
<a v-on:click="doSomething"> onclick </a>,
<a :href="url"> ... </a>
 v-bind:class="{ active: isActive }">style</div>
<div : class="{active: isActive}">style</div> 
</div>
</div>

</template>
<script>
export default {
data(){
return{
tasks: [
    {
    title: 'Task 1',
    description: 'ini deskripsi',
    isDone: false,
    }
],
    msg: "rabu sore",
    isButtonDisabled:true,
    number:10,
    ok:false,
    id:11,
    seen:true,
    url: 'https:google.com',
    isActive: true,
}
},

methods: {
    doSomething(){
        alert('hai rabu')
    }

}
}
</script>
<style>
.red{
color:blue;
}
</style>