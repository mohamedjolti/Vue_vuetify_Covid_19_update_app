<template>
  <v-card>
    <v-card-title>
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Search"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>
    <v-data-table
      :headers="headers"
      :items="desserts"
      :search="search"
      dark
    ></v-data-table>
  </v-card>
</template>

<script>
  export default {

    mounted(){
        fetch("https://corona.lmao.ninja/v2/countries").then(response=>response.json()).then((data)=>{
            console.log(data);
                    this.desserts=data
        })
    } ,
    data () {
      return {
        search: '',
        headers: [
         {text:"country",value:"country"},
         {text:"cases",value:"cases"},
         {text:"deaths",value:"deaths"},
         {text:"todayDeaths",value:"todayDeaths"},
         {text:"recovered",value:"recovered"},
         {text:"casesPerOneMillion",value:"casesPerOneMillion"},
         {text:"deathsPerOneMillion",value:"deathsPerOneMillion"},
         {text:"tests",value:"tests"},
         {text:"testsPerOneMillion",value:"testsPerOneMillion"},

],
        desserts: [
      
        ],
      }
    },
  }
</script>

<style>

</style>