<template>
  <div>
    <v-row class="pa-3">
      <v-col cols="12" md="4" offset-md="4">
        <v-card outlined class="pa-5">
          <v-form
              ref="form"
              v-model="valid"
              lazy-validation
            >
              <v-text-field
                v-model="name"
                outlined
                :counter="10"
                :rules="nameRules"
                label="Name"
                required
              ></v-text-field>

              <v-text-field
                outlined
                v-model="email"
                :rules="emailRules"
                label="E-mail"
                required
              ></v-text-field>

              <v-select
                class="mb-n6"
                outlined
                v-model="selectedCard"
                :items="creditCards"
                :rules="[v => !!v || 'Item is required']"
                label="Card type"
                required
              ></v-select>

              <v-checkbox
                v-model="checkbox"
                :rules="[v => !!v || 'You must agree to continue!']"
                label="Agree to our ridiculous terms"
                required
              ></v-checkbox>

              <v-btn
                :disabled="!valid"
                color="primary"
                depressed
                class="mt-3 mr-4"
                @click="validate"
              >
                Continue
              </v-btn>

          </v-form>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
  export default {
    data: () => ({
      valid: true,
      name: 'Test',
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
      email: 'test@test.com',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
      selectedCard: 'Visa',
      creditCards: [
        'Visa',
        'Mastercard',
        'American Exp.',
      ],
      checkbox: true,
    }),

    methods: {
      validate () {
        const isValid = this.$refs.form.validate()
        if(isValid) alert('This is a valid form')
      },
    },
  }
</script>

<style>

</style>