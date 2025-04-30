<script setup>
import { Icon } from "@iconify/vue";
</script>

<template>
    <section id="about">
        <div class="row">
            <h2>About</h2>
            <div class="text-box fade-in">
                <p>Brush of Rose painting provides high-quality painting services for both residential and commercial
                    properties, creating beautiful, lasting spaces. I also specialize in custom murals and artwork that
                    add personality and artistic flair to any environment.</p>
            </div>
            <h2>Services:</h2>
            <ol>
                <li>
                    <div>
                        <h3 class="stem-lite">
                            <Icon icon="tabler:home" /> Residential Painting:
                        </h3>
                        <ul>
                            <li class="fade-in">Interior & Exterior Painting</li>
                            <li class="fade-in">Trim, Doors, and Cabinets</li>
                            <li class="fade-in">Custom Finishes (e.g., faux finishes, textures)</li>
                            <li class="fade-in">Decorative Accents</li>
                        </ul>
                    </div>

                </li>
                <li>
                    <div>
                        <h3 class="neutral">
                            <Icon icon="tabler:building" /> Commericial Painting:
                        </h3>
                        <ul>
                            <li class="fade-in">Specialty finishes for Interior / Exterior Office Buildings</li>
                            <li class="fade-in">Specialty finishes for Interior / Exterior of Retail Spaces</li>
                            <li class="fade-in">Specialty finishes for Interior / Exterior of Restaurants and Bars</li>
                        </ul>
                        <span>* Specialty finishes = logos, decorative finishes, branding murals, etc..</span>
                    </div>

                </li>
                <li>
                    <div>
                        <h3 class="rose">
                            <Icon icon="tabler:brush" /> Murals and Artwork:
                        </h3>
                        <ul>
                            <li class="fade-in">Custom Murals for Homes, Offices, and Commercial Spaces</li>
                            <li class="fade-in">Fine Art Pieces (e.g: portraits, landscapes, or abstract art)</li>
                            <li class="fade-in">Themed Artwork for Business (e.g: branding murals)</li>
                        </ul>
                    </div>
                </li>
            </ol>
        </div>
    </section>
</template>

<style scoped>
#about {
    background-color: var(--rose-lite);
    padding-left: 8px;
    padding-right: 8px;
    width: calc(100% - 16px);
}

.rose {
    background-color: var(--rose);
}

.stem-lite {
    background-color: var(--stem-lite);
}

.neutral {
    background-color: var(--neutral);
}

.row {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
}

.bottom {
    align-self: flex-end;
    margin-top: auto;
    width: 50%;
    padding-left: 2%;
}

#about ul,
ol {
    list-style: none;
}

#about ul li {
    margin-top: 12px;
    font-family: "Dancing Script", cursive;
    font-weight: 400;
    font-style: normal;
}

#about ol li::marker {
    font-size: 42px;
}

#about svg {
    font-size: 36px;
}

#about h3 {
    line-height: 36px;
    align-items: center;
    display: flex;
    padding: 8px;
    width: calc(100% - 16px);
}
</style>
