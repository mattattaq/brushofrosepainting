<script setup>
</script>
<template>
    <header>
        <div class="container">
            <div class="header">
                <div class="logo"></div>
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
    display: flex;
    height: 150px;
    align-items: end;
}

.header {
    display: flex;
}

.logo {
    border: solid 1px black;
    width: 300px;
    height: 50px;
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
</style>
