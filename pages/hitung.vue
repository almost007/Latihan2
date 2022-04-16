<template>
<div>
  <input v-model="panjang">
  <input v-model="lebar">
<p>Message is: {{ panjang }} </p>
<p>Message is: {{ lebar }} </p>
<p>Message is: {{ luas() }} </p>
<p>Message is: {{ hasil }} </p>
</div>
</template>

<script>
export default {
  data() {
    return {

      panjang: 0,
      lebar: 0,
    }
  },
  methods: {
    plus (){
    return parseInt(this.satu)*parseInt(this.dua)
    },
    luas (){
    return parseInt(this.panjang) * parseInt(this.lebar)
    },
    luasplus (){
    return (luas()* 2)
    },
  },
  computed: {
   hasil (){
    return this.luas()
  }
  }
}
</script>