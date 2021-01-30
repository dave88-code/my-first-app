<script>

export default {
    name: "MenuItem",
    props:['addToShoppingCart', 'image', 'inStock', 'name', 'quantity']
}

</script>
<template>
    <div class="menu-item">
        <img class="menu_item_image" :src="image.source" :alt="image.alt" width="200px">
        <div>
            <h3>{{ name }}</h3>
            <p v-if="inStock">En stock</p>
            <p v-else>En rupture de stock</p>
            <div class="add-quantity">
                <label for="add-item-quantity">Quantité : {{ quantity }}</label>
                <input v-model.number="quantity" id="add-item-quantity" type="number">
                <button @click="addToShoppingCart(quantity)">Ajouter au panier</button>
            </div>
        </div>
    </div>
</template>
<style lang="scss">
    .add-quantity {
        margin: 10px;
    }
</style>