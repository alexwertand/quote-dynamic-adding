<template>
    <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
            <h3>Quote</h3>

            <textarea class="form-control" rows="5" v-model="quote"></textarea>
        </div>

        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
            <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['quotes'],
        data() {
            return{
                quote: ''
            }
        },
        methods: {
            createNew() {
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style>
    
</style>