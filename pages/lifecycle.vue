<template>
    <div>
        <p id="life"> {{msg}} </p>
        <button class="btn btn-success" @click="msg = 'text berubah'">
        Update
        </button>
    </div>
</template>
<script>

export default {
data(){
return{
    msg:'text awal',

};
},
beforeCreate() {
console.log("before created");
//console.log(document.getElementById("life"));
},
create() {
console.log("created");
console.log(document.getElementById("life").textContent);
},

beforeMount() {
console.log("before mouth");
//console.log(document.getElementById("life"));
},
mounted() {
console.log("mounth");
//console.log(document.getElementById("life"));
},
beforeUpdate() {
console.log("before update");
//console.log(document.getElementById("life"));
},
Updated() {
console.log("update");
//console.log(document.getElementById("life"));
},


}
</script>
