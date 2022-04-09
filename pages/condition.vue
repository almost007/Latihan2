<template >
<div>
<h1 v-if="num == 0"> Angkanya 0</h1>
<h1 v-else-if="num > 0"> Angkanya positive</h1>
<h1 v-else-if="num < 0"> Angkanya negative</h1>
<h1 v-else> Bukan angka 0</h1>
<h1>Title</h1>
<p>Paragraph 1</p>
<p>Paragraph 2</p>


<div v-if="ok">
    <label>username </label>
    <input placeholder="Enter your username" key="username-input:" />
    </div>

    <div v-else>
    <label>Email </label>
    <input placeholder="Enter your email" key="email-input:" />
    </div>
    <button @click="ok =!ok"> Toggle Ok </button>
    </div>

</template>

<script>
export default {
data(){
return {
num: 0,
ok: true,

}

}

   }
    </script>