<template>
<div>
<h1>Make your own Pizza!</h1>
<div class="toppings">
    <div class="topping" v-for="topping in toppings" :key="topping.id">
	<img style="display:none" :id="'topping'+topping.id" :src="'/images/toppings/'+topping.image"/>
    </div>
    <img src="/images/pizza.png"/>
    </div>
	<div class="toggles">
	<div class="toggle" v-for="topping in toppings" :key="topping.id">
		<input @change="toggle(topping.id)" type="checkbox" :checked="isChecked(topping.id)">
		<label>{{topping.name}}: {{"$"+topping.price.toFixed(2)}}</label>	
	</div>	
</div>
</div>
</template>

<script>
export default {
	name: "DesignPizza",
	props: {
		toppings: Array
},
methods: {
	toggle(id){
		let eId = 'topping'+id;
		if(document.getElementById(eId).style.display === "none"){
document.getElementById(eId).style.display = "block";
		this.$root.$data.selectedToppings.push(this.toppings[id-1])
	} else {
		this.$root.$data.selectedToppings = this.$root.$data.selectedToppings.filter((elem) => elem.id !== id)
document.getElementById(eId).style.display = "none";
}
},
isChecked(id){
	let found=false;
	this.$root.$data.selectedToppings.forEach((elem)=>{
		if(elem.id === id)
			found = true;	
})	
return found
}
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
