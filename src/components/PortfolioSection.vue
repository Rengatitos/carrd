<template>
    <section id="portfolio" class="portfolio-section">
        <div class="container">
            <header class="header">
                <h2 class="title">Portfolio</h2>
                <p class="subtitle">Proyectos rosas — limpio, moderno y con cariño</p>
            </header>

            <div class="grid">
                <article
                    v-for="project in projects"
                    :key="project.id"
                    class="card"
                    @click="openModal(project)"
                    role="button"
                    tabindex="0"
                    @keyup.enter="openModal(project)"
                >
                    <div class="thumb" :style="{ backgroundImage: `url(${project.image})` }" aria-hidden="true"></div>
                    <div class="card-body">
                        <h3 class="card-title">{{ project.title }}</h3>
                        <p class="card-desc">{{ project.short }}</p>
                        <div class="tags">
                            <span v-for="tag in project.tags" :key="tag" class="tag">{{ tag }}</span>
                        </div>
                        <div class="card-actions">
                            <button class="btn btn-primary" @click.stop="openModal(project)">Ver</button>
                            <a
                                class="btn btn-outline"
                                :href="project.repo"
                                target="_blank"
                                rel="noopener noreferrer"
                                @click.stop
                            >Código</a>
                        </div>
                    </div>
                </article>
            </div>
        </div>

        <!-- Modal / Lightbox -->
        <transition name="fade">
            <div v-if="showModal" class="modal" @click.self="closeModal">
                <div class="modal-card" role="dialog" aria-modal="true">
                    <button class="modal-close" @click="closeModal" aria-label="Cerrar">✕</button>
                    <div class="modal-media" :style="{ backgroundImage: `url(${selectedProject.image})` }"></div>
                    <div class="modal-content">
                        <h3>{{ selectedProject.title }}</h3>
                        <p class="modal-desc">{{ selectedProject.long }}</p>
                        <div class="tags">
                            <span v-for="tag in selectedProject.tags" :key="tag" class="tag">{{ tag }}</span>
                        </div>
                        <div class="modal-actions">
                            <a class="btn btn-primary" :href="selectedProject.live" target="_blank" rel="noopener noreferrer">Ver en vivo</a>
                            <a class="btn btn-outline" :href="selectedProject.repo" target="_blank" rel="noopener noreferrer">Código</a>
                        </div>
                    </div>
                </div>
            </div>
        </transition>
    </section>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const projects = [
    {
        id: 1,
        title: 'Tienda rosa',
        short: 'Landing e-commerce con animaciones suaves',
        long: 'Tienda demo hecha con enfoque en microinteracciones, experiencia móvil y un diseño muy rosa y accesible.',
        tags: ['Vue', 'CSS', 'Responsive'],
        image: 'https://picsum.photos/id/1011/800/600',
        repo: 'https://github.com/tuusuario/tienda-rosa',
        live: '#'
    },
    {
        id: 2,
        title: 'Blog pastel',
        short: 'Plantilla de blog moderna y legible',
        long: 'Plantilla de blog con tipografía optimizada, modo claro/oscuro y foco en legibilidad.',
        tags: ['Nuxt', 'Markdown'],
        image: 'https://picsum.photos/id/1015/800/600',
        repo: 'https://github.com/tuusuario/blog-pastel',
        live: '#'
    },
    {
        id: 3,
        title: 'Portfolio dinámico',
        short: 'Galería filtrable con transiciones',
        long: 'Portfolio con filtrado por categoría, animaciones suaves y soporte para galerías.',
        tags: ['Vue', 'Animations'],
        image: 'https://picsum.photos/id/1025/800/600',
        repo: 'https://github.com/tuusuario/portfolio-rosa',
        live: '#'
    },
    {
        id: 4,
        title: 'Formulario suave',
        short: 'Interacción y validación agradable',
        long: 'Formularios con validación en tiempo real y microanimaciones para mejorar la conversión.',
        tags: ['Forms', 'UX'],
        image: 'https://picsum.photos/id/1035/800/600',
        repo: 'https://github.com/tuusuario/form-rosa',
        live: '#'
    },
    {
        id: 5,
        title: 'Dashboard rosa',
        short: 'Panel limpio con datos visuales',
        long: 'Dashboard minimalista enfocado en claridad y visualización de datos relevante.',
        tags: ['Charts', 'Design'],
        image: 'https://picsum.photos/id/1041/800/600',
        repo: 'https://github.com/tuusuario/dashboard-rosa',
        live: '#'
    },
    {
        id: 6,
        title: 'Microinteracciones',
        short: 'Pequeños detalles que enamoran',
        long: 'Colección de componentes con microinteracciones que elevan la experiencia de usuario.',
        tags: ['Components', 'Motion'],
        image: 'https://picsum.photos/id/1050/800/600',
        repo: 'https://github.com/tuusuario/microinteracciones',
        live: '#'
    }
]

const showModal = ref(false)
const selectedProject = ref(projects[0])

function openModal(project) {
    selectedProject.value = project
    showModal.value = true
    document.body.style.overflow = 'hidden'
}

function closeModal() {
    showModal.value = false
    document.body.style.overflow = ''
}

function onKey(e) {
    if (e.key === 'Escape' && showModal.value) closeModal()
}

onMounted(() => window.addEventListener('keydown', onKey))
onBeforeUnmount(() => window.removeEventListener('keydown', onKey))
</script>
<style scoped lang="scss">
@import 'src/css/portfolio.scss';
</style>