<template>

    <div>
        <div class="row header" style="text-align: center; padding-top: 10px;">
            <div class="col-xl-12">
                <h4>Vue Mega Shop</h4>
            </div>
        </div>

        <div id="nav">
            <router-link to="/">Home</router-link> |
            <router-link to="/about">About</router-link>
        </div>
    </div>

</template>

<style scoped lang="scss">

    #nav {
        padding: 30px;
        text-align: center;
        font-size: 20px;

        a {
            font-weight: bold;
            color: #2c3e50;

            &.router-link-exact-active {
                color: #42b983;
            }
        }
    }
</style>

<!--<style scoped>-->
    <!--.header {-->
        <!--padding-top: 10px;-->
    <!--}-->
    <!---->
    <!--#nav {-->
        <!--padding: 30px;-->
        <!--text-align: center;-->
        <!--font-size: 20px;-->

    <!--a {-->
        <!--font-weight: bold;-->
        <!--color: #2c3e50;-->

    <!--&.router-link-exact-active {-->
         <!--color: #42b983;-->
     <!--}-->
    <!--}-->
    <!--}-->

<!--</style>-->
