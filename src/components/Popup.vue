<template>
    <div v-if="show" class="popup-container">
        <div class="popup-content">
            <button class="close-button" @click="closePopup">x</button>
            <h2>{{ title }}</h2>
            <p>{{ text }}</p>
            <p>Ukupna zarada:</p>
            <button class="delete-button" @click="handleDelete">Obriši</button>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        show: Boolean,
        title: String,
        text: String,
    },
    methods: {
        closePopup() {
            this.$emit("close");
        },
        handleDelete() {
            // You can implement the logic for the "Obriši" button click here
            console.log("Clicked on the Obriši button");
            // Add your custom logic for deleting or any other action.
        },
    },
};
</script>

<style>
/* Styles for the popup container */
.popup-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 9999;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: transparent; /* Set the background to transparent */
}

/* Styles for the popup content */
.popup-content {
    background-color: #fff;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
    position: relative; /* Add relative positioning to the popup content */
}

/* Styles for the close button */
.close-button {
    position: absolute;
    top: 10px;
    right: 10px;
    cursor: pointer;
    border: none;
    background: transparent;
    font-size: 16px;
    font-weight: bold;
}

/* Styles for the delete button */
.delete-button {
    margin-top: 10px;
    padding: 8px 16px;
    background-color: red;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
</style>
