<template>
    <div>
    <div class="product"> 
    <strong>{{product.title}}</strong>
    <p>{{product.description}}</p>
    <strong>Fiyat: {{product.price}} || Adet: {{product.count}}</strong>
     <button class="button-8" @click="addToCard(product)">Sepete Ekle</button>


    </div></div>
</template>

<script>
    export default {
        data() {
            return {   
            }
        },
       props : ["product"],
       methods: {
        addToCard(product) {
            this.$emit("addToCard", product)
            
        }
       },
       
    }
</script>

<style lang="css" scoped>
.product {
    border: 2px dashed #666;
    padding: 5px 10px;
    width: 300px;
    margin-bottom: 5px;
}

.product:hover {
    border: 2px solid #666;
    transition: all .5;
}
</style>