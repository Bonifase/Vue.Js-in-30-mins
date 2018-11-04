<template>
    <div class="home">
    <input type="text" v-model="title"><br />
        <h1>{{ title }}</h1>
        <p v-if="showName">{{ user.first_name }}</p>
        <p v-else>nobody</p>
        <v-layout row>
    <v-flex xs12 sm6 offset-sm3>
      <v-card v-for="fruit in fruits" v-bind:key="fruit">
        <v-img
          src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
          height="200px"
        >
        </v-img>

        <v-card-title primary-title>
          <div>
            <div class="headline">{{fruit.name}} <h6 class="grey--text">Price: {{fruit.price}}</h6></div>
          </div>
        </v-card-title>

      </v-card>
    </v-flex>
  </v-layout>
  <button v-on:click="buy">Order Now</button>
    </div>
</template>

<script>
export default {name: 'home',
  data () {
    return {title: 'Welcome Here',
      user: {
        first_name: 'Bonifase', last_name: 'Orwa'
      },
      showName: true,
      fruits: [
        {name: 'mango', price: 25},
        {name: 'orange', price: 30},
        {name: 'grape', price: 50},
        {name: 'aple', price: 45},
        {name: 'banana', price: 15}
      ]
    }
  },
  methods: {
    buy: function () {
      alert('Your order is being processed')
    }
  }
}
</script>

<style scoped>
ul li {
    background: #cce5ff;
    margin: 6px;
}
</style>
