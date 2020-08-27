<template>
    <div style="padding-top: 20px;">

        <form @submit.prevent="addNewProduct" class="form-group">
            <div class="row">
                <div class="offset-xl-3 col-xl-6">
                    <div class="row">
                        <div class="col-xl-6">
                            <input
                                    v-model="name"
                                    class="form-control"
                                    type="text"
                                    name="name"
                                    placeholder="Fruits...">
                        </div>
                        <div class="col-xl-6">
                            <input
                                    v-model="price"
                                    class="form-control"
                                    type="number"
                                    min="1"
                                    name="price"
                                    placeholder="$$$">
                        </div>
                    </div>
                    <div class="row" style="text-align: right; padding-top: 10px;">
                        <div class="col-xl-12">
                            <v-btn style="outline: 0"
                                   type="submit"
                                   normal
                                   rounded
                                   color="primary">Add</v-btn>

                        </div>
                    </div>

                </div>
            </div>
        </form>
    </div>
</template>

<script>

    export default {
        name: 'AddNewProduct',
        data() {
            return {
                name: '',
                price: 0
            }
        },
        methods: {
            addNewProduct() {
                var product = {
                    id: Date.now(),
                    name: this.name,
                    price: this.price,
                    isStockOut: false
                };
               this.$emit('new-product', product);
            }
        }
    }
</script>

<style scoped>

</style>
