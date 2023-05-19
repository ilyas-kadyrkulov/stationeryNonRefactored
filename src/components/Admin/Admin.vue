<template>
    <div class="admin">
        <SideBar />
        <AddPizza />
    </div>
</template>

<script>
import SideBar from "./SideBar.vue"
import AddProduct from "./AddProduct.vue"
import AddPizza from "./AddPizza.vue"
import AddScore from "./AddScore.vue"
export default {
    components: {SideBar,AddPizza}
}
</script>

<style lang="scss">
.admin{
    display: flex;

}
</style>