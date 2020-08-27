<template>
    <div style="padding-top: 20px;">
        <div class="row">
            <div class="offset-3 col-6">
                <div class="row"
                     style="font-size: 18px; font-weight: 500;"
                     v-for="(product, index) in products" v-bind:key="product.id">
                    <div class="col-7" style="padding-top: 16px;"
                         v-bind:class="{'is-stock-out': product.isStockOut}">
                        <input type="checkbox" v-on:change="makeStockOut(product)">
                        {{ index + 1 }}.  {{ product.name }}
                    </div>
                    <div class="col-4" style="text-align: right; padding-top: 16px;">
                        {{ product.price }}$
                    </div>
                    <div class="col-1">

                        <v-btn @click="$emit('delete-product', product.id)"
                               style="outline: 0"
                               rounded
                               text
                               color="error">X</v-btn>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>





<script>
    export default {
        name: 'ProductList',
        props: ['products'],
        data() {
            return {
               productList: []
            }
        },
        methods: {
            makeStockOut(product) {
                var getProduct = this.products.find(x => x.id === product.id);
                getProduct.isStockOut = !getProduct.isStockOut;
            },

            deleteProduct(product) {
                this.products = this.products.filter(x => x.id !== product.id);
            }
        }
    }
</script>




<style scoped>
    .is-stock-out {
        text-decoration: line-through;
    }
</style>
