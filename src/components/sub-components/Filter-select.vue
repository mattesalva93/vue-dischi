<template>
    <div class="col-12 d-flex justify-content-center align-items-center">
        <select name="filter-genre" id="" 
        v-model="genreSelected"
        @change="$emit('filtra', genreSelected)"
        class="mx-4"
        >
            <option value="" selected>All</option>
            <option v-for="element in listageneri" 
            :key="element" 
            :value="element">
            {{element}}</option>
        </select>
    </div>
</template>

<script>
export default {
    name: "filter-select",
    data (){
        return{
            genreSelected: "",
        }
    },
    props: {
        listageneri: Array
    }
}
</script>

<style lang="scss" scoped>

</style>