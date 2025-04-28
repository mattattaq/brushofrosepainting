<script setup>
const faqs = [
    {
        question: "How much does a custom painting or mural cost?",
        answer: "It depends on the size, detail, medium, and time required."
    },
    {
        question: "How long will it take to complete a commissioned piece?",
        answer: "Timeframes vary from a few days to several weeks depending on the piece."
    },
    {
        question: "Can I make revisions?",
        answer: "I allow one or two minor revisions; extensive changes may cost extra."
    },
    {
        question: "How much will it cost to paint my house/room/building?",
        answer: "Costs vary based on size, surface condition, paint quality, and whether it’s interior or exterior."
    },
    {
        question: "How long will the painting project take?",
        answer: "Most jobs take a few days to a week, depending on the scale and weather (for exteriors)."
    },
    {
        question: "Do I need to move my furniture or prep the area beforehand?",
        answer: "It’s often recommended to clear small or fragile items ahead of time. A small fee will be added for moving furniture or trimming foliage."
    },
    {
        question: "What kind of paint do you use, and can I choose the color/brand?",
        answer: "High-quality, durable paint, and yes—clients usually choose the colors and sometimes the brand."
    },
    {
        question: "Will you do prep work like filling holes, sanding, or priming?",
        answer: "Yes, prep work is typically included to ensure a smooth, lasting finish."
    },
    {
        question: "How do you protect furniture, floors, and landscaping?",
        answer: "Drop cloths, plastic sheeting, and painter’s tape to protect everything."
    },
    {
        question: "Do you offer any warranties or guarantees?",
        answer: "I offer limited warranties on their work, usually covering peeling or blistering within a specific timeframe."
    },
    {
        question: "Is the paint safe for kids, pets, and people with allergies?",
        answer: "Most painting brands offer low-VOC or no-VOC paints that are safer for sensitive environments."
    },
    {
        question: "Do you require a deposit?",
        answer: "Yes, typically 10–30% upfront with the balance due upon completion."
    }
]
</script>

<template>
    <section id="faq">
        <div class="container">
            <h2>Frequently Asked Questions</h2>
            <div v-for="(faq, index) in faqs" :key="index" class="faq-item">
                <h3>{{ index + 1 }}. {{ faq.question }}</h3>
                <p>{{ faq.answer }}</p>
            </div>
        </div>
    </section>
</template>

<style scoped>
#faq {
    background-color: #f9f9f9;
    text-align: center;
    width: 100%;
}

.container {
    max-width: 800px;
    margin: 0 auto;
    flex-direction: column;
}

.faq-item {
    background-color: #fff;
    padding: 15px;
    margin-bottom: 10px;
    border-radius: 5px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

h2 {
    font-size: 2rem;
    margin-bottom: 2rem;
}

h3 {
    font-size: 1.5rem;
    color: #333;
    margin-bottom: 1rem;
}

p {
    font-size: 1rem;
    color: #666;
}
</style>
