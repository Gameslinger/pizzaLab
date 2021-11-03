<template>
<div>
<h1>Make your own Pizza!</h1>
<div class="toppings">
    <div class="topping" v-for="topping in toppings" :key="topping.id">
	<img :src="'/images/toppings/'+topping.image"/>
    </div>
    <img src="/images/pizza.png"/>
    </div>
</div>
</template>

<script>
export default {
	name: "DesignPizza",
	props: {
		toppings: Array
}
}
</script>	

<style scoped>
.toppings .topping{
display:flex;
justify-content:center;
}

.topping img {
position: absolute;

}
</style>
