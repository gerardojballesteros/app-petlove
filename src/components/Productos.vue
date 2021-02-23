<template>
    <div class="productos">
        <div class="wrap-productos">
            <b-card-group class="card" v-for="todo in todos" :key="todo.id">
                <b-card id="card-b">
                <b-card-text>
                    <img class="img-card" :src="todo.photo" alt="">
                    <div class="txt-products">
                        <div class="wrap-txt">
                            <p class="name-products"> {{ todo.name }} </p>
                             <p class="price-products"> {{ todo.price }} CLP</p>
                        </div>
                    </div>
                </b-card-text>
                <div class="btn-counter">
                        <div class="wrap-counter">
                            <div id="countercart" class="increment">
                                <a id="suma" v-on:click="counter -= 1" href="#">-</a>
                                <p id="conteo">{{ counter }}</p>
                                <a id="resta" v-on:click="counter += 1" href="#" >+</a>
                            </div>
                            <div class="cart">
                                <img src="../assets/shopping-cart.svg" alt="">
                            </div>
                        </div>
                    </div>
                </b-card>
                
            </b-card-group>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    name: '#countercart',
    data(){
        return{
            todos:null,
            counter: 0
        }
    },
    mounted(){
        this.getTodos();
    },
    methods: {
        getTodos(){
            axios
            .get('http://sva.talana.com:8000/api/product/')
            .then( response => {
                this.todos = response.data
            })
            .catch( e=> console.log(e))
        }
    }
    
};



</script>


<style scoped>
.productos{
    width: 100%;
    height: auto;
}
.productos .wrap-productos{
    height: 90vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
.card{
    width: 240px;
    height: 400px;
    overflow: hidden;
    display: flex;
    align-items: center;
    margin: 0 10px;
    border: none;
}
.img-card{
    width: 140px;
    max-width: 140px;
    max-height: 140px;
}

.txt-products{
    width: 100%;
    height: 150px;
    display: flex;
    align-items:flex-end;
    text-align: start;
}

.txt-products p{
    font-size: 24px;
    margin-top: 20px;

}
#app > div.content > div.productos > div > div:nth-child(4) > div > div > img{
    width: 100px;
    max-height: 160px;
}
.price-products{
    font-weight: 500;
    font-size: 20px!important;
}

.btn-counter{
    width: 100%;
    height: auto;
}
.wrap-counter{
    width: 160px;
    height: 40px;
    border: 2px solid #FE7676;
    border-radius: 10px;
    display: flex;
    overflow: hidden;
}

.increment{
    width: 50%;
    height: 40px;
    display: flex;
}
.cart{
    width: 50%;
    height: 40px;
    background: #FE7676;
    display: flex;
    justify-content: center;
}
.cart img{
    width: 24px;
}

#countercart{
    font-size: 24px;
    padding: 0 14px;
}
#conteo{
    margin: 0 5px;
}
#card-b{
    border: 1px solid rgb(225, 225, 225);
}
</style>