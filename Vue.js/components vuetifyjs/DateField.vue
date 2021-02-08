<template>
	<v-dialog
		ref="dialog"
		v-model="modal"
		:return-value.sync="date"
		width="290px"
	>
		<template v-slot:activator="{ on, attrs }">
			<v-text-field
				append-icon="mdi-calendar"
				@click:append="open()"
				v-bind="attrs"
				v-model="view"
				:label="alias"
				hide-details
				readonly
				outlined
				v-on="on"
				dense
			/>
		</template>
		<v-date-picker
			@input="select($event)"
			v-model="date"
			locale="sp-br"
			show-adjacent-months
		>
			<v-spacer></v-spacer>

			<v-btn text color="primary" @click="getToday()">
				HOJE
			</v-btn>
		</v-date-picker>
	</v-dialog>
</template>

<script>
	import moment from "moment";
	export default {
		props: {
			alias: {},
		},

		data: () => ({
			date: null,
			modal: false,
			view: null,
		}),

		methods: {
			open() {
				this.modal = true
			},

			getToday() {
				this.date = moment().format("YYYY-MM-DD");
				this.select(this.date)
			},

			select(event) {
				this.view = moment(event).format("DD/MM/YYYY")
				this.$emit("input", event);
				this.modal = false
			}
		},
	}
</script>
<style>

</style>