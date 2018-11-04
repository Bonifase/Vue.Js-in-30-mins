<template>
    <div class="home">
    <input type="text" v-model="title"><br />
        <h1>{{ title }}</h1>
        <p v-if="showName">{{ user.first_name }}</p>
        <p v-else>nobody</p>
        <v-layout row>
    <v-flex xs12 sm6 offset-sm3>
      <v-card v-for="fruit in fruits" v-bind:key="fruit">
        <v-card-title primary-title>
          <div>
            <div class="headline">{{fruit.name}} <h6 class="grey--text">Price: {{fruit.price}}</h6></div>
          </div>
        </v-card-title>
      </v-card>
    </v-flex>
  </v-layout>
  <button v-on:click="buy">Order Now</button>
  <hr />
  <label>First Name: </label><input type="text" v-model="user.first_name"><br>
  <label>Last Name: </label><input type="text" v-model="user.last_name">
  <h2>{{full_name}}</h2>
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
        {name: 'grape', price: 50}
      ]
    }
  },
  methods: {
    buy: function () {
      alert('Your order is being processed')
    },
    presskey: function (e) {
      console.log(e.target.value)
    }
  },
  computed: {
    full_name: function () {
      return this.user.first_name + ' ' + this.user.last_name
    }
  }
}
</script>

<style scoped>
button {
    background: #85b7ee;
    margin: 10px;
}
</style>
