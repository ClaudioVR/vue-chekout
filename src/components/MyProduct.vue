<template>
  <div>
    <v-row class="green">
      <v-col class="" cols="12" md="8">
        <v-card flat class="pa-3">
          <p class="text-h5">Handlekurv</p>
          <v-row>
            <v-col cols="3">
              <v-img
                contain
                src="@/assets/shoes.jpg"
              ></v-img>
            </v-col>
            <v-col cols="6">
              <p class="my-0 text-body-1 font-weight-bold">Top dog trainers</p>
              <p class="my-0 grey--text">Black gentleman's shoes</p>
              <p class="my-0 grey--text">Size: 46</p>
              <p class="mt-3 mb-0 primary--text">Raskere leveranse</p>
            </v-col>
            <v-col class="" cols="4" offset="8" md="3" offset-md="0">
              <v-card flat class="pa-3">
                <v-select
                  dense
                  outlined
                  :items="amount"
                  v-model="selectedAmount"
                ></v-select>
                <div class="text-right">
                  <p class="text-body-1 font-weight-bold">{{ totalPrice }}</p>
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
      <v-col class="" cols="12" md="8">
        <v-card flat class="pa-3">
        <p class="text-h5">Forventet levering</p>
        <p>{{ arrivalDate }}</p>
        </v-card>
      </v-col>
      <v-col class="" cols="12" md="8">
        <v-card flat class="pa-3">
        <p class="text-h5">Vi aksepterer</p>
        <div class="d-flex">
          <v-card v-for="x in 5" :key="x" height="50" width="60" class="red mr-3">
            
          </v-card>
        </div>
        </v-card>
      </v-col>
    </v-row>
      
  </div>
</template>

<script>
export default {
  name: 'myProduct',
  data() {
    return {
      amount: [1, 2, 3, 4, 5],
      selectedAmount: 1
    }
  },
  computed: {
    totalPrice() {
      const price = 399
      let totalPrice = this.selectedAmount * price
      let formatter = new Intl.NumberFormat('no-NO', {
        style: 'currency',
        currency: 'NOK'
    });
    return formatter.format(totalPrice)
    },
    arrivalDate() {
      let todaysDate = new Date()
      let deliveryDate = todaysDate.setDate(todaysDate.getDate() + 4 * 7);
      return new Date(deliveryDate).toLocaleDateString("no-No")
    }
  }
}
</script>

<style>

</style>