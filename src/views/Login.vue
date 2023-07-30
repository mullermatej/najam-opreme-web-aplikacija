<template>
    <v-main>
        <v-container fluid>
            <v-row justify="center" align="center" class="mt-5">
                <v-col cols="12" md="6">
                    <v-card elevation="3" class="login-card">
                        <v-card-title class="text-center">
                            <h1 class="display-1">Ulogiraj se</h1>
                        </v-card-title>
                        <v-card-text>
                            <v-form>
                                <v-text-field
                                    v-model="email"
                                    label="Korisničko ime"
                                    prepend-icon="mdi-account-circle"
                                    outlined
                                    required
                                ></v-text-field>
                                <v-text-field
                                    v-model="password"
                                    :type="showPassword ? 'text' : 'password'"
                                    label="Šifra"
                                    prepend-icon="mdi-lock"
                                    :append-icon="
                                        showPassword ? 'mdi-eye' : 'mdi-eye-off'
                                    "
                                    @click:append="showPassword = !showPassword"
                                    outlined
                                    required
                                ></v-text-field>
                            </v-form>
                        </v-card-text>
                        <v-divider></v-divider>
                        <v-card-actions>
                            <v-btn color="info">-></v-btn>
                        </v-card-actions>
                    </v-card>
                </v-col>
            </v-row>
        </v-container>
    </v-main>
</template>

<script>
export default {
    name: "Login",

    data() {
        return {
            email: "",
            password: "",
            showPassword: false,
        };
    },

    methods: {
        loginUser() {
            // Implement your login logic here
            // You can access the entered data using the respective data properties
            // For example, you can make an API call to your backend to authenticate the user
        },
    },
};
</script>

<style scoped>
.login-card {
    background-color: #f9f9f9;
    border-radius: 10px;
    padding: 30px;
}
</style>
