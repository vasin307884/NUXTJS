<template>
  <v-layout row wrap xs12>
    <v-flex xs12 sm6 md6>
      <v-card flat outlined class="pl-sm-4 pl-md-8 d-flex">
        <h1>{{check1}}</h1>
        <v-checkbox v-model="check1" class="mx-2" label="box1"></v-checkbox>
        <v-checkbox v-model="check2" class="mx-2" label="box2"></v-checkbox>
        <v-checkbox v-model="check3" class="mx-2" label="box3"></v-checkbox>
      </v-card>
    </v-flex>
    <v-flex xs12 sm6 md6>
      <v-card flat outlined class="pl-sm-4 pl-md-8">
        <h1>Card2</h1>
        <v-text-field
          :disabled="!check1"
          v-model="firstname"
          label="Firstname"
          placeholder="firstname"
        ></v-text-field>
      </v-card>
    </v-flex>
    <v-flex xs12 sm12 md6>
      <v-card>
        <v-card-title>
          <v-text-field v-model="search" label="Search" single-line hide-details></v-text-field>
        </v-card-title>
        <v-data-table :headers="headers" :items="desserts" :search="search"></v-data-table>
      </v-card>
    </v-flex>
    <v-flex xs12 sm6 md6>
      <v-card class="my-10">
        <v-card-title>
          <v-text-field v-model="search" label="Search" single-line hide-details></v-text-field>
        </v-card-title>
        <v-data-table :headers="empheaders" :items="emplist" :search="search" :employee="employee"></v-data-table>
      </v-card>
    </v-flex>
  </v-layout>
</template>
<script>
export default {
  data() {
    return {
      search: "",
      headers: [
        {
          text: "Dessert (100g serving)",
          align: "left",
          filterable: true,
          value: "name"
        },
        { text: "Calories", value: "calories" },
        { text: "Fat (g)", value: "fat" },
        { text: "Carbs (g)", value: "carbs" },
        { text: "Protein (g)", value: "protein" },
        { text: "Iron (%)", value: "iron" }
      ],
      empheaders: [
        {
          text: "Employee ID",
          align: "left",
          filterable: true,
          value: "id"
        },
        { text: "Firstname", value: "first_name" },
        { text: "Lastname", value: "last_name" },
        { text: "Email", value: "email" },
        { text: "Gender", value: "gender" },
        { text: "IP-address", value: "ip_address"}
      ],
      emplist: [
        {
          id: 1,
          first_name: "Guillaume",
          last_name: "Keeney",
          email: "gkeeney0@istockphoto.com",
          gender: "Male",
          ip_address: "115.37.248.255"
        },
        {
          id: 2,
          first_name: "Ruprecht",
          last_name: "Stansell",
          email: "rstansell1@bizjournals.com",
          gender: "Male",
          ip_address: "62.206.93.175"
        },
        {
          id: 3,
          first_name: "Franklin",
          last_name: "Scadding",
          email: "fscadding2@soundcloud.com",
          gender: "Male",
          ip_address: "109.112.64.106"
        },
        {
          id: 4,
          first_name: "Prue",
          last_name: "Winny",
          email: "pwinny3@loc.gov",
          gender: "Female",
          ip_address: "18.254.151.193"
        },
        {
          id: 5,
          first_name: "Emmi",
          last_name: "Kesterton",
          email: "ekesterton4@sciencedaily.com",
          gender: "Female",
          ip_address: "13.230.25.58"
        }
      ],
      desserts: [
        {
          name: "Frozen Yogurt",
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          iron: "1%"
        },
        {
          name: "Ice cream sandwich",
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          iron: "1%"
        },
        {
          name: "Eclair",
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          iron: "7%"
        },
        {
          name: "Cupcake",
          calories: 305,
          fat: 3.7,
          carbs: 67,
          protein: 4.3,
          iron: "8%"
        },
        {
          name: "Gingerbread",
          calories: 356,
          fat: 16.0,
          carbs: 49,
          protein: 3.9,
          iron: "16%"
        },
        {
          name: "Jelly bean",
          calories: 375,
          fat: 0.0,
          carbs: 94,
          protein: 0.0,
          iron: "0%"
        },
        {
          name: "Lollipop",
          calories: 392,
          fat: 0.2,
          carbs: 98,
          protein: 0,
          iron: "2%"
        },
        {
          name: "Honeycomb",
          calories: 408,
          fat: 3.2,
          carbs: 87,
          protein: 6.5,
          iron: "45%"
        },
        {
          name: "Donut",
          calories: 452,
          fat: 25.0,
          carbs: 51,
          protein: 4.9,
          iron: "22%"
        },
        {
          name: "KitKat",
          calories: 518,
          fat: 26.0,
          carbs: 65,
          protein: 7,
          iron: "6%"
        }
      ],
      check1: false,
      check2: false,
      check3: true,
      myname: "vasin",
      clipped: false,
      drawer: false
    };
  },
  watch: {
    check1: function(n, o) {
      if (n == true) {
        this.check2 = false;
        this.check3 = false;
      }
    },
    check2: function(n, o) {
      if (n == true) {
        this.check1 = false;
        this.check3 = false;
      }
    },
    check3: function(n, o) {
      if (n == true) {
        this.check1 = false;
        this.check2 = false;
      }
    }
  }
};
</script>
