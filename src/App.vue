<template>
  <v-app>
    <div class="container-fluid">
      <Header/>
      <router-view/>
    </div>
  </v-app>
</template>

<script>
    import Header from './components/Header';

    export default {
        components: {
            Header
        }
    }
</script>
