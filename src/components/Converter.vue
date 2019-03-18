<template>
    <div class="conveter">

        <h2>{{coinA}} &rarr; {{coinB}}</h2>
        <input type="text"  v-model="coinA_value" :placeholder="coinA">
        <input type="button" value="Converter"  v-on:click="converter">
        <h2>{{coinB_value}}</h2>
    </div>
</template>

<script>
    export default {
        name : "Converter",
        props: ["coinA","coinB"],

        data(){
            return {
                coinA_value: "",
                coinB_value: 0
            };
        },

        methods:{
            converter() {
                let from_to = this.coinA + "_" + this.coinB;
                let url = "http://free.currencyconverterapi.com/api/v5/convert?q=" + from_to + "&compact=y" + "&apiKey=2ea71b06aa1ba9e77423";

                fetch(url).then(res => {
                    return res.json();
                }).then(json => {
                        let price = json[from_to].val;
                        this.coinB_value = (price * parseFloat(this.coinA_value)).toFixed(2);
                    })
            }
        }
    };

</script>

<style scoped>
    .converter{
        max-width: 300px;
        padding: 20px;
        box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    }

</style>