<template>
        <div class="container-fluid" id="app">
            <div class="row">
                <div class="col-xl-12">
                    <AddNewProduct v-on:new-product="addNewProduct"/>
                    <ProductList v-bind:products="products"
                                 v-on:delete-product="deleteProduct"/>
                </div>
            </div>
        </div>
</template>

<script>

    import ProductList from './ProductList';
    import AddNewProduct from './AddNewProduct';
    import axios from 'axios';

    export default {
        name: 'App',
        components: {
            ProductList,
            AddNewProduct
        },
        data() {
            return {
                getProductsUrl: 'https://my-json-server.typicode.com/SanjidHaque/Fake-Product-Server/products',
                products: []
            }
        },
        methods: {
            addNewProduct(product) {
                this.products.push(product);
            },
            deleteProduct(id) {
                this.products = this.products.filter(x => x.id !== id);
            }
        },
        created() {
            axios.get(this.getProductsUrl)
                .then(response => {
                    this.products = response.data;
                }).catch(error => console.log(error));
        }
    }
</script>

<style>

</style>
