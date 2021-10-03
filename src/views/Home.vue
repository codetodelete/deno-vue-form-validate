<template>
  <v-container>
    <v-row class="text-center">
      <v-col class="mb-4">
        <h1 class="font-weight-bold mb-3">
          Login form with validate using Vue + Vuetify
        </h1>

        <v-card
			    class="mx-auto my-12"
			    max-width="374"
			  >
			    <template slot="progress">
			      <v-progress-linear
			        color="deep-purple"
			        height="10"
			        indeterminate
			      ></v-progress-linear>
			    </template>

			    <v-img
			      height="200"
			      src="@/assets/group.png"
			      contain
			    ></v-img>

			    <v-card-text>
			      <v-row
			        align="center"
			        class="mx-0"
			      >
			        <v-col
		            cols="12"
		          >
		            <v-text-field
		              v-model="form.username"
		              :rules="rules.username"
		              color="purple darken-2"
		              label="Username"
		              prepend-inner-icon="mdi-account"
		              required
		            ></v-text-field>
		          </v-col>
		          <v-col
		            cols="12"
		          >
		            <v-text-field
		              v-model="form.password"
		              :rules="rules.password"
		              color="blue darken-2"
		              label="Password"
		              prepend-inner-icon="mdi-lock"
		              required
		            ></v-text-field>
		          </v-col>
		          <v-col cols="12">
		            <v-checkbox
		              v-model="form.remember"
		              color="green"
		            >
		              <template v-slot:label>
		                <div @click.stop="">
		                  Remember me
		                </div>
		              </template>
		            </v-checkbox>
		          </v-col>
		          <v-col
		            cols="12"
		          >
		            <v-btn
					        color="deep-purple lighten-2"
					        dark
					        @click="reserve"
					        block
					        :loading="loading"
					      >
					        Login
					      </v-btn>
		          </v-col>
			      </v-row>
			    </v-card-text>
			  </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      loading: false,
      selection: 1,
      form: {
      	username: '',
        password: '',
        remember: ''
      },
      rules: {
        username: [val => (val || '').length > 0 || 'This field is required'],
        password: [val => (val || '').length > 0 || 'This field is required'],
      },
    }),

    methods: {
      reserve () {
        this.loading = true

        setTimeout(() => (this.loading = false), 2000)
      },
    },
  }
</script>
