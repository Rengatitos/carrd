<template>
  <nav class="nav-links">
    <a href="#about" class="nav-item" @click.prevent="scrollTo('about')">ABOUT ME</a>
    <a href="#portfolio" class="nav-item" @click.prevent="scrollTo('portfolio')">PORTFOLIO</a>
    <a href="#gallery" class="nav-item" @click.prevent="scrollTo('gallery')">GALLERY</a>
    <a href="#contact" class="nav-item" @click.prevent="scrollTo('contact')">CONTACT ME</a>
  </nav>

  <section id="about">
    <HomeMain />
  </section>

  <section id="portfolio">
    <PortfolioSection />
  </section>

  <section id="gallery">
    <GallerySection />
  </section>

  <section id="contact">
    <ContactSection />
  </section>


</template>

<script setup>
import HomeMain from 'src/components/Aboutme.vue'
import PortfolioSection from 'src/components/PortfolioSection.vue'
import GallerySection from 'src/components/GallerySection.vue'
import ContactSection from 'src/components/ContactSection.vue'

function scrollTo (id) {
  const el = document.getElementById(id)
  if (el) {
    el.scrollIntoView({ behavior: 'smooth', block: 'start' })
    try {
      history.replaceState(null, '', `#${id}`)
    } catch (e) {
      // ignore
    }
  }
}
</script>

<style scoped lang="scss">
@import 'src/css/nav.scss';
</style>