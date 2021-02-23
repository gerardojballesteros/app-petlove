<template>
    <div class="categorias">
        <div class="title-cat">
            <h1>Categorias</h1>
        </div>
        <ul>
            <li v-for="todo in todos" :key="todo.id">
                <a href="">{{ todo.name }}</a>
            </li>
        </ul>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return{
            todos:null
        }
    },
    mounted(){
        this.getTodos();
    },
    methods: {
        getTodos(){
            axios
            .get('http://sva.talana.com:8000/api/product-category/')
            .then( response => {
                this.todos = response.data
            })
            .catch( e=> console.log(e))
        }
    }
}
</script>

<style scoped>
.categorias{
    width: 350px;
    height: 100vh;
    -webkit-box-shadow: 3px 0px 5px 0px rgba(0,0,0,0.25);
    -moz-box-shadow: 3px 0px 5px 0px rgba(0,0,0,0.25);
    box-shadow: 3px 0px 5px 0px rgba(0,0,0,0.25);
}
.title-cat{
    margin-top: 30px;
}
.title-cat h1{
    color: #FE7676;
}
.categorias ul{
    list-style: none;
    margin-top: 40px;
}
.categorias ul li{
    text-align: start;
    padding-left: 20px;
    margin: 14px 0
}
.categorias ul li a{
    font-size: 20px;
    color: rgb(97, 97, 97);
}
</style>