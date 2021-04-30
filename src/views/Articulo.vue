<template>
    <titulo :texto="articulo.title"/>
    <h2> Parametro : {{ $route.params.id }}</h2>
    <h3> {{ articulo.title }} </h3>
    <p> {{ articulo.id }} - {{ articulo.body }} </p>
</template>
<script>
import Titulo from '../components/Titulo'

export default {
    components: {
        Titulo
    },
    data () {
       return {
           articulo: {},
       }
   },
   methods: {
       /**
        * Consumir solo un articulo del API usando el ID del URL
        * 
        * /
       /*
       async consumirArticulo() {
           try{
                const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
                const objeto = await data.json()
                
                this.articulo = objeto
           }catch(e){
               return e.message
           }
       }*/
       
       
       // TODO: HAcer fetch de TODOS los articulos y filtrar por el id de la ruta. Investigar metodos find/filterX/map/foreach 
       
       
    //    /**
    //     * Consumir todos los articulos del API y buscar en un array con filter().
    //     * 
    //     * @return {Array}
    //     */
    //    async consumirArticulo() { 
    //        try{
    //            const data = await fetch('https://jsonplaceholder.typicode.com/posts')
    //            const array = await data.json()
    //            this.articulo = array.filter(item => {
    //                return item.id == this.$route.params.id
    //            })
    //        }catch(e){
    //            return e.message
    //        } 
    //    },
       
    //    /**
    //     * Consumir todos los articulos del API y buscar en un array con find().
    //     * 
    //     * @return {Object}
    //     */
    //    async consumirArticulo() { 
    //        try{
    //            const data = await fetch('https://jsonplaceholder.typicode.com/posts')
    //            const array = await data.json()
    //            this.articulo = array.find(item => item.id == this.$route.params.id)      
    //        }catch(e){
    //            return e.message
    //        } 
    //    },
    
    
    
    
   },
   
   /**
    * The component's created lifecycle hook.
    *
    * @return {void}
    */
   created() {
       this.consumirArticulo()
   }
}
</script>

<style>

</style>
