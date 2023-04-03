<template>

    <div class="container">
        <!--   <myComp />  -->
        <div class="cart">
            <h3>Alışveriş SEPETİ</h3>
            <ul>
                <li v-for="item in cartİtems" :key="item.id">{{ item.title }}</li>
              

            </ul>
            <p v-if="cartİtems.length == 0">SEPETİNİZ BOŞTUR</p>
        </div>
        <product @addToCart="cartİtems.push($event)" :product="product" v-for="product in productlList" :key="product.id" />
      

    </div>

</template>


<script>
import MainContainer from './MainContainer.vue';
import product from './components/product.vue';
export default {
    components: {
        myComp: MainContainer,
        product
    },
    data() {
        return {
            productlList: [{
                id: 1,
                title: "MacBook Pro",
                price: 100,
                count: 0,
                description: "Açıklama 1"
            },
            {
                id: 2,
                title: "İphone 14",
                price: 100,
                count: 100,
                description: "Açıklama 2"
            },
            {
                id: 3,
                title: "Lenova",
                price: 100,
                count: 1000,
                description: "Açıklama 3"
            },
            ],
            cartİtems:["MackBook" , "İphone", "Lenova"]

        }
    }

}
</script>

<style>
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;


}
.cart{
    margin-bottom: 50px;
    text-align: center;

}
</style>