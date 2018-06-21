<template>
  <div>
    <city-header></city-header>
    <city-search :cities="this.cities"></city-search>
    <city-list 
      :cities="this.cities" 
      :hotCities="this.hotCities" 
      :letter="this.letter"
      >
    </city-list>
    <city-alphabet 
    @change="handleLetterChange" 
    :cities="this.cities"
    >
    </city-alphabet>
   
  </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data (){
    return{
      cities: {},
      hotCities: [],
      letter: '',
      touchStatus: false,
    }
  },
  methods:{
    getListInfo (){
      axios.get('api/city.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res){
      res = res.data      
      this.cities = res.data.cities
      this.hotCities = res.data.hotCities
    },
    handleLetterChange (e){
      this.letter = e
    }
  },
  mounted (){
    this.getListInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
