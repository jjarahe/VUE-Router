<template>
   <Titulo texto="Titulo de mi Blog"/>
   <!--<button @click= "consumirAPI">Consumir API</button>-->
   
    <div v-for="(item, index) in arrayBlog" :key="index">
        <router-link :to="`/blog/${item.id}`" >
                {{ item.id }} - {{ item.title }}
        </router-link>
    </div>
   
   
</template>

<script> 
import Titulo from '../components/Titulo'
export default {
   components: {
       Titulo
   },
   data () {
       return {
           arrayBlog: []
       }
   },
   methods: {
       async consumirAPI() {
           try{
                const data = await fetch('https://jsonplaceholder.typicode.com/posts')
                const array = await data.json()
                this.arrayBlog = array

           }catch(e){
               console.log(e)
               return e
           }
       }
   },
   created() {
       this.consumirAPI()
   }
}
</script>

<style>

</style>
