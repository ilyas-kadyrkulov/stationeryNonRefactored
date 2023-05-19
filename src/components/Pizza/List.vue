<template>
<div v-for="pizza in filteredPizzas" :key="pizza.id" >
    <Item :pizza="pizza" />
</div>
</template>

<script>
import { computed } from '@vue/runtime-core'
import { useStore } from 'vuex'

import Item from "./Item.vue"

export default {
    props: ["pizzas"],
    components: {Item},
    setup(props) {
        const store = useStore()

        const filteredPizzas = computed(() => {
            return props.pizzas.filter((pizza) => pizza.name.includes(store.state.searchValues))
        })

        return{
            filteredPizzas
        }
    }
}
</script>

<style scoped>
div {
    width: 280px;
    position: relative;
    margin: 0 35px 65px 0;
}
div:nth-child(4n) {
    margin-right: 0;
}
div:last-child {
    margin-right: 0;
}
</style>