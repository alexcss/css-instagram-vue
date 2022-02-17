<template>
	<div class="ba-filter">
		<div class="ba-filter__top">
			<label :for="id">{{filter.label}}:</label>
			<span class="ba-filter__value">{{filter.value + filter.unit}}</span>
		</div>
		<!-- /.ba-filter__top -->
		<input class="range" :id="id" type="range" @input="change" v-model="filter.value" :min="filter.min" :max="filter.max" >
	</div>
	<!-- /.ba-filter -->	
</template>

<script>

export default {
	emits: ['change'],
	props: ['filter', 'id'],
	data() {
		return{

		}
	},
	methods:{
		change(){
			const value = this.filter.value + this.filter.unit;
			this.$emit('change', this.id, value)
		},

	}
}
</script>