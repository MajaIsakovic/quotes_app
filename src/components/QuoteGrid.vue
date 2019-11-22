<template>
  <div class="row">
      <app-quote v-bind:key="quote" v-for="quote in quotes"> {{ quote }}</app-quote>
  </div>
</template>

<script>
    import Quote from '../components/Quote.vue';

    export default {
        props: ['quotes'],
        components:{
            'app-quote': Quote
        }
    }
</script>