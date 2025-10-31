<template>
	<q-page class="about-page q-pa-lg">
		<!-- Small in-page nav to match the Canva header -->
		<nav class="nav-links">
			<a href="#" class="nav-item">ABOUT ME</a>
			<a href="#" class="nav-item">PORTFOLIO</a>
			<a href="#" class="nav-item">GALLERY</a>
			<a href="#" class="nav-item">CONTACT ME</a>
		</nav>

		<div class="about-container">
			<div class="left">
				<div class="tama-frame">
					<img src="src/assets/dog-placeholder.png" alt="profile" class="tama-img" />
				</div>
			</div>

			<div class="right">
				<!-- Decorative heading graphic could be an image; fallback to text -->
				<div class="dam-heading">
					<!-- If you have a graphic file put it in src/assets/dam-logo.png and uncomment -->
					<!-- <img src="~assets/dam-logo.png" alt="dam" class="dam-logo"/> -->
					<span class="dam-text">dam</span>
				</div>

				<h2 class="intro-title">Hi! I am Dam. I love drawing, <strong>I'm 21 yo</strong>, and I'm an IT student at ESAN.</h2>

				<p class="intro-text">You can use any pronouns for me. I also have a special talent — I can crack my thumbs!</p>

				<div class="socials">
					<a class="social" href="#" aria-label="Instagram">IG</a>
					<a class="social" href="#" aria-label="Facebook">f</a>
					<a class="social" href="#" aria-label="Twitter">t</a>
					<a class="social" href="#" aria-label="LinkedIn">in</a>
				</div>
			</div>
		</div>
	</q-page>
</template>

<script setup>
// Página simple; no lógica necesaria por ahora.
</script>

<style lang="scss" scoped>
.about-page {
	min-height: calc(100vh - 64px);
	/* Dotted/polka background similar to the design */
	background-color: #fffaf6;
	background-image: radial-gradient(rgba(200,150,150,0.06) 1px, transparent 1px);
	background-size: 22px 22px;
	color: #8b3b3b;
}

.nav-links {
	display: flex;
	justify-content: center;
	gap: 48px;
	margin-bottom: 28px;
}

.nav-item {
	color: #d94b4b;
	font-weight: 700;
	text-transform: uppercase;
	letter-spacing: 1px;
	text-decoration: none;
	font-size: 0.95rem;
}

.about-container {
	display: flex;
	gap: 36px;
	align-items: center;
	justify-content: center;
	flex-wrap: wrap;
}

.left {
	flex: 0 1 460px;
	display: flex;
	align-items: center;
	justify-content: center;
}

.tama-frame {
	width: 480px;
	height: 420px;
	border-radius: 28% 72% 58% 42% / 46% 36% 64% 54%;
	/* playful pink container */
	background: linear-gradient(180deg,#ffd6e6 0%, #ffeef6 60%);
	display: flex;
	align-items: center;
	justify-content: center;
	padding: 28px;
	box-shadow: 0 10px 30px rgba(0,0,0,0.08);
	position: relative;
}

.tama-img {
	width: 75%;
	height: auto;
	border-radius: 12px;
	object-fit: cover;
	background: white;
	padding: 6px;
}

.right {
	flex: 1 1 420px;
	max-width: 560px;
}

.dam-heading {
	display: flex;
	align-items: center;
	margin-bottom: 10px;
}

.dam-text {
	font-size: 3.2rem;
	color: #f2a6c0;
	font-weight: 700;
	text-transform: lowercase;
	letter-spacing: 6px;
}

.intro-title {
	color: #b83b3b;
	font-size: 1.15rem;
	font-weight: 500;
	margin: 8px 0 12px 0;
}

.intro-text {
	color: #c35a5a;
	line-height: 1.6;
	margin-bottom: 18px;
}

.socials {
	display: flex;
	gap: 10px;
	align-items: center;
}

.social {
	display: inline-flex;
	align-items: center;
	justify-content: center;
	width: 44px;
	height: 44px;
	border-radius: 8px;
	background: #fff1f4;
	color: #b83b3b;
	text-decoration: none;
	font-weight: 700;
}

@media (max-width: 900px) {
	.tama-frame { width: 340px; height: 300px; }
	.dam-text { font-size: 2.2rem; }
	.about-container { gap: 20px; }
}

@media (max-width: 600px) {
	.tama-frame { width: 260px; height: 220px; padding: 18px; }
	.nav-links { gap: 18px; font-size: 0.85rem; }
	.about-container { flex-direction: column; }
	.right { text-align: center; }
}

</style>

