<script setup>
</script>
<template>
    <header>

        <div class="container">
            <div class="header">
                <img class="logo-img" src="../assets/brush-of-rose-no-text.jpg" alt="Brush of Rose Painting Logo">
                <div class="logo">Brush Of Rose Painting</div>
                <ul>
                    <li><a href="#splash">Top</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#gallery">Gallery</a></li>
                    <li><a href="#book">Book Now</a></li>
                </ul>
            </div>
        </div>
    </header>
</template>

<style scoped>
header {
    width: 100%;
    min-height: 150px;
    display: flex;
    align-items: end;
}

.header {
    display: flex;
    align-items: center;
}

.logo {
    font-family: "Staatliches", sans-serif;
    font-size: 28px;
    color: var(--rose);
    width: 250px;
}

.logo-img {
    height: 100px;
    display: block;
    margin-right: 12px;
}

header ul {
    list-style: none;
    display: flex;
    width: auto;
}

header ul li {
    display: inline;
    margin-right: 5%;
    font-weight: bold;
    width: auto;
    min-width: 75px;
    font-family: "Staatliches", sans-serif;
    font-weight: 400;
    font-style: normal;
    line-height: 32px;
}

header ul li a {
    color: grey;
    text-decoration: none;
}

header ul li a:hover {
    color: var(--rose);
    transition: color 0.5s;
}

@media screen and (max-width: 768px) {
    .header {
        display: block;
        margin: 0 auto;
    }

    .logo-img {
        margin: 0 auto;
    }

    .logo {
        text-align: center;
        width: 100%;
    }
}
</style>
