<template>
  <div>
   <p>Your pizza with {{toppingNames}} costs ${{price.toFixed(2)}} </p>
  </div>
</template>

<script>
export default {
	name: "CartView",
	computed: {
	price(){
          return this.$root.$data.selectedToppings.reduce((prev, current) => {
		return prev+current.price;
            },10)
          },
	toppingNames(){
          return this.$root.$data.selectedToppings.reduce((prev,current) => {
              return prev+ ", " +current.name;
         },"Cheese")
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
