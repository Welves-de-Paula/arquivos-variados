<template>
	<div>
		<v-text-field
			ref="field"
			type="text"
			v-bind="$attrs"
			v-currency="options"
			v-model="formatedNumber"
			@focus="$event.target.select()"
			@keypress="handleKeypress($event)"
		/>
	</div>
</template>

<script>

	export default {
		props: {
			defaultValue: {
				default: 0
			},
			value: {},
			precision: {
				default: 2
			},
			allowNegative: {
				default: false
			}
		},

		data: () => ({
			formatedNumber: 0
		}),

		computed: {
			options() {
				return {
					locale: "de-DE",
					distractionFree: false,
					"auto-decimal-mode": false,
					currency: null,
					precision: this.precision,
					allowNegative: this.allowNegative,
				};
			}
		},

		watch: {
			formatedNumber: {
				deep: true,
				handler() {
					this.$emit("input", this.getFormData());
				},
			},
		},


		methods: {

			getFormData() {

				let value = JSON.parse(JSON.stringify(this.formatedNumber))


				value = (value) ? value.replace(/\D/g, '') : 0;

				return value
			},


			handleKeypress(event) {

				if (event.keyCode == '46') { // period
					// todo corrigir teclados mobile sansumg, utilizar ponto como virgula
				}
			}
		}
	};
</script>

