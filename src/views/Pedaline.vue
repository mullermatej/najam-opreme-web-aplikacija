<template>
    <v-main>
        <div class="header-container">
            <h1>Pedaline</h1>
            <button class="add-button" @click="handleAddClick">+</button>
        </div>

        <div class="image-row">
            <!-- Loop through the imageContainers array -->
            <div
                v-for="(image, index) in imageContainers"
                :key="index"
                class="image-container"
            >
                <a
                    href="#"
                    class="pedalboatLink"
                    @click="handlePedalboatClick($event, image.title)"
                >
                    <div class="pedalboatCard">
                        <img :src="image.src" class="smaller-image" />
                        <h3>{{ image.title }}</h3>
                    </div>
                </a>
            </div>
        </div>

        <Popup
            v-if="showPopup"
            :show="showPopup"
            :title="popupTitle"
            :text="popupText"
            @close="showPopup = false"
        />
    </v-main>
</template>

<script>
import Popup from "@/components/Popup.vue";

export default {
    components: {
        Popup,
    },
    data() {
        return {
            showPopup: false,
            popupTitle: "",
            popupText: "Izdana: ne",
            imageContainers: [
                // Initial image container data
                {
                    title: "#A1",
                    src: "/Users/matejmuller/Desktop/faks/treca godina/Zavrsni rad aplikacija/najam_opreme/src/assets/Pedalboat.png",
                },
                { title: "#A2", src: "@/assets/Pedalboat.png" },
                { title: "#A3", src: "@/assets/Pedalboat.png" },
            ],
        };
    },
    methods: {
        handlePedalboatClick(event, title) {
            console.log(`Clicked on pedalboat card with title ${title}`);
            this.popupTitle = `Pedaline ${title}`; // Set the popupTitle with "Pedaline" and the clicked title
            this.showPopup = true; // Show the popup
        },
        handleAddClick() {
            console.log("Clicked on the + button");
            // Create a new image container with a unique title
            const newTitle = `#A${this.imageContainers.length + 1}`;
            this.imageContainers.push({
                title: newTitle,
                src: "@/assets/Pedalboat.png",
            });
        },
    },
};
</script>

<style>
/* Styles for the header container */
.header-container {
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 100px;
}
/* Styles for the image row */
.image-row {
    display: flex;
    align-items: center;
    justify-content: center;
}

/* Styles for the image container */
.image-container {
    text-align: center;
    margin: 0 10px; /* Add some spacing between the image containers */
}

/* Styles for the pedalboatCard */
.pedalboatCard {
    display: inline-block;
    /* Make the div inline and adjust its width to the content (the image) */
    text-align: center;
}

/* Styles for the image */
.smaller-image {
    width: 130px; /* Adjust the width to the desired size */
    height: auto; /* This maintains the aspect ratio */
    margin: 0; /* Remove the left margin for the image */
}

/* Styles for the heading */
h1 {
    font-size: 70px;
    margin-right: 20px;
}

/* Styles for the clickable link */
.pedalboatLink {
    text-decoration: none; /* Remove the default underline style for links */
    color: inherit; /* Inherit the text color from the parent element */
}

/* Styles for the circular add button */
.add-button {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background-color: #007bff; /* Adjust the background color as needed */
    color: #fff; /* Adjust the text color as needed */
    font-size: 24px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: none;
    cursor: pointer;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}
</style>
