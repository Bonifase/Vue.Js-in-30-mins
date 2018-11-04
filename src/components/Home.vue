<template>
    <div class="home">
    <input type="text" v-model="title"><br />
        <h1>{{ title }}</h1>
        <p v-if="showName">{{ user.first_name }}</p>
        <p v-else>nobody</p>
        <v-layout>
    <v-flex xs12 sm6 offset-sm3>
      <v-card v-for="fruit in fruits" v-bind:key="fruit">
        <v-img
          src="https://cdn.vuetifyjs.com/images/cards/desert.jpg"
          aspect-ratio="2.75"
        ></v-img>

        <v-card-title primary-title>
          <div>
            <h3 class="headline mb-0">Name: {{fruit.name}}</h3>
            <div>Price: {{fruit.price}}</div>
          </div>
        </v-card-title>

        <v-card-actions>
          <v-btn flat color="orange">Buy</v-btn>
          <v-btn flat color="orange">Details</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
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
  }
}
</script>

<style scoped>
ul li {
    background: #cce5ff;
    margin: 6px;
}
</style>
