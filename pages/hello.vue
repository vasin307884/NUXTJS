<template>
  <v-img src="https://i.redd.it/y1ostvqnr4711.jpg" height="100%" weight="100%">
    <v-form>
    <v-container class="my-10">
      <v-card class="mx-auto" max-width="600" max-height="800" outlined>
        <v-container class="text-center">
          <h1>Register</h1>
          <v-row justify="center">
            <v-col cols="12" sm="6">
              <v-text-field v-model="fname" label="Firstname" placeholder="Firstname"></v-text-field>
              <v-text-field v-model="lname" label="Lastname" placeholder="Lastname"></v-text-field>
              <v-text-field v-model="pw" label="Password" type="password" placeholder="password"></v-text-field>
              <v-text-field v-model="email" label="Email" type="email" placeholder="Email"></v-text-field>
              <v-text-field v-model="phone" label="Phone" placeholder="Phone-number"></v-text-field>

              <div class="my-5">
                <v-btn rounded color="pink" dark>Sign-up</v-btn>
              </div>
             <div class="my-5">
                <v-btn text small>Already have an account? Sign-in</v-btn>
              </div>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
      </v-container>
    </v-form>
  </v-img>
</template>
<script>
export default {
  data() {
    return {
      myname: "vasin",
      clipped: false,
      drawer: false
    };
  }
};
</script>
