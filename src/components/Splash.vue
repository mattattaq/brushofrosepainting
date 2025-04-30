<script setup>
</script>

<template>
    <section id="splash">
        <div class="container">
            <div class="half text-center">
                <img src="../assets/mural.jpg" class="fill-available"
                    alt="A trailer with a beatiful yellow, blue, pink, and white flowers painted on a field of grey. To the right a monarch butterfly and to the left a bee.">
            </div>
            <div class="half col text-center">
                <h1 class="text-stretch">Bringing <b>Heart</b> into Every <b>Hue</b></h1>
                <a href="#book" class="book" alt="Click this button to navigate to the booking form">Book Now!</a>
            </div>
        </div>
    </section>
</template>

<style scoped>
h1 {
    width: 100%;
    display: block;
}

.book {
    width: 100%;
    display: block;
    flex-direction: column;
}

.text-center {
    text-align: center;
    align-items: center;
}

.book {
    background-color: var(--stem-lite);
    width: 150px;
    position: relative;
    padding: 8px;
    border-radius: 5px;
    font-size: 24px;
    text-decoration: none;
    font-family: "Dancing Script", cursive;
    font-weight: 400;
    font-style: normal;
    color: white;
    margin: 0 auto;
}

.book:hover {
    background-color: var(--neutral);
}

.fill-available {
    width: -webkit-fill-available;
}

#splash {
    background-color: var(--rose);
}

.text-stretch {
    font-size: xxx-large;
}
</style>
