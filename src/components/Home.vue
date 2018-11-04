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
            <div class="headline">Name: {{fruit.name}}</div>
            <span class="grey--text">Price: {{fruit.price}}</span>
          </div>
        </v-card-title>

        <v-card-actions>
          <v-btn flat>Share</v-btn>
          <v-btn flat color="purple">Explore</v-btn>
          <v-spacer></v-spacer>
          <v-btn icon @click="show = !show">
            <v-icon>{{ show ? 'keyboard_arrow_down' : 'keyboard_arrow_up' }}</v-icon>
          </v-btn>
        </v-card-actions>

        <v-slide-y-transition>
          <v-card-text v-show="show">
            I'm a thing. But, like most politicians, he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.
          </v-card-text>
        </v-slide-y-transition>
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
