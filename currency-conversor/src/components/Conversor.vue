<template>
    <div class="conversor">
        <h2>{{ currencyA }} to {{ currencyB }}</h2>
        <input type="text" v-model="currencyA_value"  v-bind:placeholder="currencyA">
        <input type="button" value="Convert" v-on:click="convert" >
        <h2>{{ currencyB_value }}</h2>
    </div>
</template>

<script>
export default {
    name: "Conversor",
    props: ["currencyA", "currencyB"],
    data(){
        return{
            currencyA_value : "",
            currencyB_value : 0
        }
    },

    methods:{
        convert(){
            let from_to = this.currencyA + "_" + this.currencyB

            let url = "https://free.currconv.com/api/v7/convert?q="+
                from_to
            +"&compact=ultra&apiKey=898a47777ef9a569267c"        

            fetch(url).then(res => {
                return res.json();
            })

            .then(json => {
                let currency = json[from_to];
                this.currencyB_value = (currency * parseFloat(this.currencyA_value)).toFixed(2)
            })
        }

    }
    
};
</script>

<style scoped>
.conversor{
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}


</style>>
