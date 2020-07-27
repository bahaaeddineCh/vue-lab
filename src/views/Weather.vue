<template>
  <div class="weather">
    <div class="container">
        <form>
        <div class="form-group">
            <label for="">City</label>
            <input type="text" class="form-control" v-model="city"  placeholder="Enter ur city">
        </div>

        <button class="btn btn-primary" @click.prevent="getData">get Weather</button>

        <div class="container">
            <h1>{{ city }}</h1>
            <p>Weather:</p>
        </div>
    </form>
  </div>
    </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'

export default {
  name: 'Blog',
  data() {
    return {
      weather: '',
      temp: 0,
      city: '',
    }
  },

  methods: {
    getData(){
      var cmp = this;
      axios.get('https://api.openweathermap.org/data/2.5/weather?q='+ this.city +'&appid=1aa4632f2fb015e9977dec8cb17e2589')
          .then(function (response) {
            cmp.posts = response.data;
          })
          .catch(function (error) {
            console.log(error);
          })
          .then(function () {
            // always executed
          });
    }
  },

}
</script>