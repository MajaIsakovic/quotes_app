<template>
  <div>
      <app-quote v-bind:index="index" v-bind:key="index" v-for="(quote, index) in quotes"
                 @click.native="quoteDelete(index)"> {{ quote }}</app-quote>
  </div>
</template>

<script>
    import Quote from '../components/Quote.vue';

    export default {
        props: ['quotes'],
        components:{
            'app-quote': Quote
        },
        methods:{
            quoteDelete(index){
                this.$emit('quoteDeleted', index);
            }
        }
    }
</script>