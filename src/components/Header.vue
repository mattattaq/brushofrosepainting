<script setup>
</script>
<template>
    <header>
        <ul>
            <li><a href="#splash">Top</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#gallery">Gallery</a></li>
            <li><a href="#book">Book Now</a></li>
        </ul>
    </header>
</template>

<style scoped>
header {
    position: fixed;
    width: 100%;
    display: flex;
    height: 50px;
    background-color: var(--rose);
    z-index: 101;
    top: 0;
}

header ul {
    list-style: none;
    display: flex;
    width: 100%;
}

header ul li {
    display: inline;
    margin-right: 5%;
    font-weight: bold;
    width: auto;
}

header ul li a {
    color: white;
    text-decoration: none;
}

header ul li a:hover {
    color: var(--stem);
    font-weight: bold;
}
</style>
