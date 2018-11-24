<template>
	<div id="app">
		<div class="container">
			<app-header :quotesCount="quotes.length" :maxQuotes="maxQuotes"></app-header>

			<app-new-quote @quoteAdded="newQuote"></app-new-quote>

			<app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>

			<div class="row">
				<div class="col-sm-12">
					<div class="alert alert-info">Info: Click in a Quote to delete it! </div>
				</div>
			</div>

			<hr>

			<hr>

			<hr>

			<app-simple-form></app-simple-form>

			<hr>

			<hr>

			<hr>

			<hr>
		</div>
	</div>
</template>

<script>
	//import HelloWorld from './components/HelloWorld.vue'

	import QuoteGrid from './components/QuoteGrid.vue'
	import NewQuote from './components/NewQuote.vue'
	import Header from './components/Header.vue'
	import SimpleForm from './components/SimpleForm.vue'

	export default {
		name: 'app',
		data() {
			return {
				quotes: [
					'Just a Quote to see something'
				],
				maxQuotes: 10
			}
		},
		methods: {
			newQuote(quote) {
				if (this.quotes.length >= this.maxQuotes) {
					return alert('Please delete Quotes first!');
				}

				this.quotes.push(quote);
			},
			deleteQuote(index) {
				this.quotes.splice(index, 1);
			}
		},
		components: {
			appHeader: Header,
			appNewQuote: NewQuote,
			appQuoteGrid: QuoteGrid,
			appSimpleForm: SimpleForm
		}
	}
</script>

<style>
</style>
