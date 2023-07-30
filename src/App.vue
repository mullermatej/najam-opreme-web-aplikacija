<template>
    <v-app>
        <v-app-bar app>
            <!-- Header title -->
            <v-app-bar-title>
                <v-row align="center">
                    <v-btn
                        v-for="item in items"
                        :key="item.title"
                        @click="navigateTo(item.route)"
                        class="mr-4"
                        text
                        style="font-size: 15px"
                    >
                        {{ item.title }}
                    </v-btn>
                </v-row>
            </v-app-bar-title>
        </v-app-bar>

        <v-main>
            <router-view />
        </v-main>
    </v-app>
</template>

<script>
export default {
    name: "App",

    data: () => ({
        items: [
            { title: "Home", icon: "mdi-home", route: "/" },
            { title: "About Us", icon: "mdi-information", route: "/about" },
            { title: "Shop", icon: "mdi-cart", route: "/shop" },
            { title: "Blog", icon: "mdi-newspaper", route: "/blog" },
            { title: "Contact Us", icon: "mdi-email", route: "/contact" },
        ],
    }),

    methods: {
        navigateTo(route) {
            // You can add navigation logic here to handle the route clicks
            // For example, using Vue Router: this.$router.push(route)
        },
    },
};
</script>
