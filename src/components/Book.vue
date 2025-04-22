<script setup>
import { ref } from 'vue'

const name = ref('')
const email = ref('')
const message = ref('')

function sendEmail() {
    const subject = encodeURIComponent(`Booking Inquiry from ${name.value}`)
    const body = encodeURIComponent(`Name: ${name.value}\nEmail: ${email.value}\n\nMessage:\n${message.value}`)
    const mailtoLink = `mailto:your@email.com?subject=${subject}&body=${body}`

    window.location.href = mailtoLink
}
</script>

<template>
    <section id="book">
        <h3 class="text-center">If you'd like to book me fill this out to send me an email.</h3>

        <form @submit.prevent="sendEmail" class="form">
            <label>
                Name:
                <input type="text" v-model="name" required />
            </label>

            <label>
                Email:
                <input type="email" v-model="email" required />
            </label>

            <label>
                Message:
                <textarea v-model="message" required></textarea>
            </label>

            <button type="submit">Send Email</button>
        </form>
    </section>
</template>

<style scoped>
#book {
    background: linear-gradient(104deg, rgba(42, 123, 155, 1) 0%, rgba(87, 199, 133, 1) 77%, rgba(237, 221, 83, 1) 100%);
    display: block;
    padding-top: 12px;
    padding-bottom: 12px;
}

.text-center {
    text-align: center;
}

.form {
    display: flex;
    flex-direction: column;
    gap: 12px;
    max-width: 400px;
    margin: 0 auto;
    padding: 16px;
}

input,
textarea {
    width: 100%;
    padding: 8px;
    border-radius: 4px;
    border: 1px solid #ccc;
}

button {
    background-color: #2A7B9B;
    color: white;
    border: none;
    padding: 10px;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #215e74;
}
</style>
