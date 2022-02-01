<template>
    <div class="col-12 d-flex justify-content-center align-items-center">
        <select name="genre" 
        v-model="genreSelected"
        @change="$emit('filtra', genreSelected)" 
        >
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    name: "Genre-select",
    data (){
        return{
            genreSelected: "",
        }
    },
}
</script>

<style lang="scss" scoped>

</style>