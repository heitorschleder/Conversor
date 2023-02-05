<template>
    <div class="conversor">
        <h2>{{moedaA}} para {{moedaB}}</h2>
        <input type="text" v-model="moedaA_value" :placeholder="moedaA">
        <input type="button" value="Converter" @click="converter">
        <h2>{{moedaB_value}}</h2>
    </div>
</template>

<script>
export default {
    name: "conversor_moeda",
    props:["moedaA","moedaB"],
    data() {
        return{
            moedaA_value: "",
            moedaB_value: 0
        };
    },
    methods:{
        converter (){
            let de_para = this.moedaA + "-" + this.moedaB;
            let url = 
            "https://economia.awesomeapi.com.br/json/last/" + de_para;
            fetch(url).then(res => {return res.json()})
            .then(json=>{
                var moedas = this.moedaA + this.moedaB;
                let cotacao = parseFloat(json[moedas].high).toFixed(2);
                this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2)
            }).catch(()=>{console.log("ERROU")});
        }
    }
};
</script>

<style scoped>
  
</style>