<template>
    <v-main>
        <h1 class="text-center mt-4">IZBORNIK NAJMA OPREME</h1>
        <v-container class="mt-4">
            <!-- First Row of Buttons -->
            <v-row justify="center">
                <v-btn
                    @click="handleButtonClick('Plaža')"
                    class="mb-4 square-button"
                    :style="squareButtonStyle"
                >
                    <h2 class="mb-0">Plaža</h2>
                </v-btn>
                <v-btn
                    @click="handleButtonClick('Pedaline')"
                    class="mb-4 square-button"
                    :style="squareButtonStyle"
                >
                    <h2 class="mb-0">Pedaline</h2>
                </v-btn>
                <v-btn
                    @click="handleButtonClick('Kajaci')"
                    class="mb-4 square-button"
                    :style="squareButtonStyle"
                >
                    <h2 class="mb-0">Kajaci</h2>
                </v-btn>
            </v-row>

            <!-- Second Row of Buttons -->
            <v-row justify="center">
                <v-btn
                    @click="handleButtonClick('Supovi')"
                    class="mb-4 square-button"
                    :style="squareButtonStyle"
                >
                    <h2 class="mb-0">Supovi</h2>
                </v-btn>
                <v-btn
                    @click="handleButtonClick('Gliseri')"
                    class="mb-4 square-button"
                    :style="squareButtonStyle"
                >
                    <h2 class="mb-0">Gliseri</h2>
                </v-btn>
                <v-btn
                    @click="handleButtonClick('UFO')"
                    class="mb-4 square-button"
                    :style="squareButtonStyle"
                >
                    <h2 class="mb-0">UFO</h2>
                </v-btn>
            </v-row>

            <!-- Third Row of Buttons -->
            <v-row justify="center">
                <v-btn
                    @click="handleButtonClick('Paragliding')"
                    class="mb-4 square-button"
                    :style="squareButtonStyle"
                >
                    <h2 class="mb-0">Paragliding</h2>
                </v-btn>
                <v-btn
                    @click="handleButtonClick('Tube')"
                    class="mb-4 square-button"
                    :style="squareButtonStyle"
                >
                    <h2 class="mb-0">Tube</h2>
                </v-btn>
                <v-btn
                    @click="handleButtonClick('Vesla')"
                    class="mb-4 square-button"
                    :style="squareButtonStyle"
                >
                    <h2 class="mb-0">Vesla</h2>
                </v-btn>
            </v-row>
        </v-container>
    </v-main>
</template>

<script>
export default {
    name: "Home",

    components: {},

    data() {
        return {
            squareButtonStyle: {
                width: "calc(100% / 3 - 32px)", // Each button occupies one-third of the container minus the margin
                height: "calc(100% / 3 - 32px)", // Each button occupies one-third of the container minus the margin
                padding: "60px",
                fontSize: "45px", // Adjust the font size as needed
            },
        };
    },

    methods: {
        handleButtonClick(title) {
            // Handle the button click event here
            console.log(`Clicked on ${title}`);
            // You can perform any logic or route to different pages based on the title if needed
        },
    },
};
</script>

<style>
h1 {
    text-align: center;
    font-size: 50px;
}

.square-button {
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>
