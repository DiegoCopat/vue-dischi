<template>
    <header>
        <div>
            <img src="../assets/images/spotify.png" alt="">
        </div>
        <div>
            <select v-model="genreSelected"
            @change="$emit('changeGenre', genreSelected)">
                <option value="">seleziona un genere</option>
                <option v-for="(genre, index) in genres" :key="index"
                :value="genre">{{ genre }}</option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name: "Header",
    data: function() {
        return {
            genreSelected: ""
        }
    },
     props: {
        "genres": Array
    }
}
</script>

<style lang="scss" scope>
    Header {
        display: flex;
        justify-content: space-between;
        padding: 0 15px;

        div {
            display: flex;
            height: 100%;
            align-content: center;

            img {
                height: 80%;
                margin: auto 0
            }

            select {
                height: 30px;
                margin: auto 0;
                padding: 5px;
            }
        }
    }

</style>