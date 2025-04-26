<script setup>
import { Icon } from "@iconify/vue";  
</script>

<template>
    <footer>
        <div class="container">
            <a href="https://www.facebook.com/profile.php?id=61568301927136" target="_blank"
                alt="Brush Of Rose Painting Facebok">
                <Icon icon="logos:facebook" />
            </a>
            <a href="mailto:brushofrosepainting@gmail.com" target="_blank" alt="Email me">
                <Icon icon="logos:google-gmail" />
            </a>
            <a href="tel:+11111" alt="Call now">
                <Icon icon="emojione:mobile-phone" />
            </a>
            <p>&copy; brushofrosepainting 2025</p>
        </div>
    </footer>
</template>

<style scoped>
footer {
    background-color: white;
    color: var(--neutral);
    padding: 10px;
    min-height: 100px;
    border-top: 25px solid;
    border-image: linear-gradient(to right, var(--rose) 25%, var(--rose-lite) 25%, var(--rose-lite) 50%, var(--stem-lite) 50%, var(--stem-lite) 75%, var(--neutral) 75%) 5;
}

footer svg {
    margin-right: 10px;
    margin-left: 20px;
    font-size: 24px;
}

footer .container {
    height: auto;
    align-items: center;
}
</style>
