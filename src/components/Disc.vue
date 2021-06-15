<template>
    <div class="element">
        <img :src="discElement.poster" alt="">
        <h2> {{ discElement.title }} </h2>
        <h4> {{ discElement.author }} </h4>
        <h4> {{ discElement.year }} </h4>
    </div>
</template>

<script>
export default {
    name: "Disc",
    props: {
        discElement: Object
    }
}
</script>

<style lang="scss" scope>
@import "../style/General";

    .element {
        width: 18%;
        background-color: $bg-header;
        margin-bottom: 20px;
        text-align: center;
        padding: 5px;

        img {
            width: 100%;
        }

        h2 {
            font-size: 15px;
            text-transform: uppercase; 
            padding: 10px 5px 15px 5px;
        }

        h4 {
            font-size: 14px;
            color: $text-gray;

            &:last-child {
                font-size: 12px;
                padding-bottom: 10px;
            }
        }
    }

</style>