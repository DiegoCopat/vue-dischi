<template>
    <main>
        <section class="wrapper">
            <Disc 
                v-for="(element, index) in elements" :key="index"
                :discElement="element" />
        </section>
    </main>
</template>

<script>
import Disc from "./Disc";
import axios from "axios";

export default {
    name: "Main",
    data: function() {
        return {
            elements: [],
            genres: []
        }
    },
    components: {
        Disc
    },
    created: function() {
        axios
            .get("https://flynn.boolean.careers/exercises/api/array/music")
            .then(
                response => {
                    console.log(response.data);
                    this.elements = response.data.response;
                    console.log(this.elements);

                    this.elements.forEach(
                        (element) => {
                            if(!this.genres.includes(element.genre)) {
                                this.genres.push(element.genre);
                            }
                        }
                    );
                    console.log(this.genres);

                    this.$emit("ready", this.genres);
                    
                }
            )
            .catch(
                error => {
                    console.log(error);
                }
            );
    },
    
}
</script>

<style lang="scss" scope>

    main {
        display: flex;
        
    }
    .wrapper {
        display: flex;
        flex-wrap: wrap;
        width: 80%;
        height: 80%;
        margin: auto;
        padding: 30px 0;
        justify-content: space-between;
    }
</style>