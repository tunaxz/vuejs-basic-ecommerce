<template>
  <div>
<div class="container">
  <div class="card">

<h2>Sepet</h2>
  <ul>
  <li v-for="item in cardItems" :key="item">{{item.title}}</li>
  </ul>
  <p v-if="cardItems.length == 0">Sepetiniz Boştur. Alışverişe Hemen Başlayabilirsiniz</p>
  </div>  
  <Product @addToCard="cardItems.push($event)"  :product="product" v-for="product in productList" :key="product.id"/>
  </div>
    </div>

</template>

<script>
import Product from "@/components/Product"
  export default {
    components: {
            Product: Product,
            
        },
        data() {
          return {
                            productList : [
                {
                   id: "1",
                    title: "MacBook Pro",
                    price: 10000,
                    count: 10,
                    description: "Şimdiye kadarki en güçlü Mac laptoplar ve masaüstü bilgisayarlar"
                },
                {
                   id: "2",
                    title: "Iphone",
                    price: 1000,
                    count: 100,
                    description: "Şimdiye kadarki en güçlü Telefonlar al bence yani"
                },
                {
                   id: "3",
                    title: "Keyboard",
                    price: 10,
                    count: 1000,
                    description: "Bok gibi bir keyboard sakın alma yani bence öğğh"
                },
                 
                ],

                cardItems: []
          }
        },
  }
</script>

<style lang="css" scoped>
.container{
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 5px;
  flex-direction: column;
}
.card{
  margin-bottom: 50px;
}
</style>