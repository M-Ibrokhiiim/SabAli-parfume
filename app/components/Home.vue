
<template>
  <div class="home">

    <!-- HERO SECTION -->
    <section class="hero">
      <div class="overlay"></div>

      <div class="hero-content">
        <h1 class="brand">NOIR ÉLÉGANCE</h1>
        <p class="tagline">Luxury fragrances crafted for timeless presence</p>
        <button class="cta">Explore Collection</button>
      </div>
    </section>

    <!-- FEATURE SECTION -->
    <section class="features">
      <div class="feature">
        <h2>Signature Scents</h2>
        <p>Exclusive perfumes designed with rare ingredients from around the world.</p>
      </div>

      <div class="feature">
        <h2>Luxury Packaging</h2>
        <p>Minimal, elegant bottles crafted to reflect modern sophistication.</p>
      </div>

      <div class="feature">
        <h2>Limited Editions</h2>
        <p>Seasonal collections available in strictly limited quantities.</p>
      </div>
    </section>

    <!-- COLLECTION PREVIEW -->
    <section class="collection">
      <h2>Featured Collection</h2>

      <div class="grid">
        <div class="card">
          <div class="img"></div>
          <h3>Midnight Oud</h3>
          <p>Deep, smoky and sensual</p>
        </div>

        <div class="card">
          <div class="img"></div>
          <h3>Velvet Rose</h3>
          <p>Soft floral elegance</p>
        </div>

        <div class="card">
          <div class="img"></div>
          <h3>Amber Noir</h3>
          <p>Warm, rich and bold</p>
        </div>
      </div>
    </section>

    <!-- FOOTER -->
    <footer class="footer">
      <p>© 2026 NOIR ÉLÉGANCE. All rights reserved.</p>
    </footer>

  </div>
</template>

<style scoped>
.home {
  font-family: 'Inter', sans-serif;
  color: #111;
}

/* HERO */
.hero {
  height: 100vh;
  background: url('https://images.unsplash.com/photo-1541643600914-78b084683601') center/cover no-repeat;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.overlay {
  position: absolute;
  inset: 0;
  background: rgba(0,0,0,0.45);
}

.hero-content {
  position: relative;
  color: white;
}

.brand {
  font-size: 64px;
  letter-spacing: 8px;
  font-weight: 300;
}

.tagline {
  margin-top: 12px;
  font-size: 18px;
  opacity: 0.85;
}

.cta {
  margin-top: 24px;
  padding: 12px 28px;
  border: 1px solid white;
  background: transparent;
  color: white;
  cursor: pointer;
  transition: 0.3s;
}

.cta:hover {
  background: white;
  color: black;
}

/* FEATURES */
.features {
  display: flex;
  justify-content: space-around;
  padding: 80px 40px;
  background: #fafafa;
}

.feature {
  max-width: 300px;
  text-align: center;
}

/* COLLECTION */
.collection {
  padding: 80px 40px;
  text-align: center;
}

.grid {
  display: flex;
  gap: 30px;
  justify-content: center;
  margin-top: 40px;
}

.card {
  width: 220px;
}

.img {
  height: 280px;
  background: #ddd;
  margin-bottom: 12px;
}

/* FOOTER */
.footer {
  padding: 40px;
  text-align: center;
  background: #111;
  color: white;
}
</style>
