<template>
  <div class="header-outer">
    <header class="glass-pill">

      <!-- Logo -->
      <div class="logo">
        <svg class="hex-icon" viewBox="0 0 100 115" fill="none">
          <path d="M50 4L96 29V86L50 111L4 86V29L50 4Z"
                fill="rgba(255,255,255,0.16)"
                stroke="rgba(255,255,255,0.72)"
                stroke-width="3.5"/>
          <text x="50" y="73" text-anchor="middle"
                fill="white" font-size="46"
                font-style="italic"
                font-family="Playfair Display, Georgia, serif">A</text>
        </svg>
        <span class="logo-name">Antonin <em>Koreta</em></span>
      </div>

      <!-- Nav -->
      <nav aria-label="Navigation principale">
        <a href="#about">Qui suis-je ?</a>
        <a href="#portfolio">Projets</a>
      </nav>

      <!-- CTA -->
      <a href="#contact" class="cta-btn">Contact</a>

      <!-- Mobile burger -->
      <button class="burger" aria-label="Menu" @click="menuOpen = !menuOpen">
        <span></span><span></span><span></span>
      </button>

    </header>

    <!-- Mobile menu -->
    <div class="mobile-menu" :class="{ open: menuOpen }">
      <a href="#about"     @click="menuOpen = false">Qui suis-je ?</a>
      <a href="#portfolio" @click="menuOpen = false">Projets</a>
      <a href="#process"   @click="menuOpen = false">Processus</a>
      <a href="#contact"   @click="menuOpen = false">Contact</a>
    </div>
  </div>
</template>

<script setup>
const menuOpen = ref(false)
</script>

<style scoped>
/* ── Wrapper ── */
.header-outer {
  position: relative;
  z-index: 10;
  width: calc(100% - 40px);
  max-width: 920px;
  margin: 0 auto;
  padding-top: 24px;
}

/* ── Header bar — no background ── */
.glass-pill {
  position: relative;
  display: flex;
  align-items: center;
  padding: 10px 4px;
  border-radius: 0;
  overflow: visible;
  gap: 0;
  background: none;
  backdrop-filter: none;
  -webkit-backdrop-filter: none;
  border: none;
  box-shadow: none;
}


/* ── Logo ── */
.logo {
  display: flex;
  align-items: center;
  gap: 9px;
  flex-shrink: 0;
  position: relative;
  z-index: 1;
  padding: 0 16px 0 4px;
}

.hex-icon {
  width: 32px;
  height: 32px;
  flex-shrink: 0;
  filter: drop-shadow(0 1px 3px rgba(0,0,0,0.18));
}

.logo-name {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 15px;
  font-weight: 400;
  font-style: italic;
  color: #ffffff;
  white-space: nowrap;
  letter-spacing: 0.01em;
  text-shadow: 0 1px 10px rgba(8, 28, 50, 0.45);
}

.logo-name em {
  font-weight: 700;
  font-style: italic;
}


/* ── Nav ── */
nav {
  display: flex;
  align-items: center;
  gap: 4px;
  flex: 1;
  justify-content: center;
  position: relative;
  z-index: 1;
}

nav a {
  font-family: 'Playfair Display', Georgia, serif;
  font-style: italic;
  font-size: 14.5px;
  font-weight: 500;
  color: #ffffff;
  text-decoration: none;
  padding: 6px 16px;
  border-radius: 999px;
  white-space: nowrap;
  text-shadow: 0 1px 10px rgba(8, 28, 50, 0.5);
  transition: opacity 0.2s ease, background 0.22s ease;
}

nav a:hover {
  opacity: 0.65;
  background: rgba(255, 255, 255, 0.1);
}

/* ── CTA ── */
.cta-btn {
  font-family: 'Public Sans', sans-serif;
  font-style: normal;
  font-size: 14px;
  font-weight: 500;
  letter-spacing: 0.01em;
  display: inline-flex;
  align-items: center;
  color: #ffffff;
  text-decoration: none;
  border-radius: 999px;
  padding: 10px 26px;
  white-space: nowrap;
  flex-shrink: 0;
  margin-left: 8px;
  background: #0a1628;
  color: #ffffff;
  backdrop-filter: none;
  -webkit-backdrop-filter: none;
  border: none;
  box-shadow: 0 2px 14px rgba(8, 28, 50, 0.14);
  transition: background 0.22s ease, box-shadow 0.22s ease, transform 0.28s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.cta-btn:hover {
  background: #162540;
  box-shadow: 0 4px 20px rgba(8, 28, 50, 0.30);
  transform: translateY(-1px);
}

/* ── Burger ── */
.burger {
  display: none;
  flex-direction: column;
  gap: 4.5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 6px 8px;
  position: relative;
  z-index: 1;
  flex-shrink: 0;
}

.burger span {
  display: block;
  width: 18px;
  height: 1.5px;
  background: rgba(255, 255, 255, 0.92);
  border-radius: 2px;
}

/* ── Mobile menu ── */
.mobile-menu {
  display: none;
  flex-direction: column;
  gap: 2px;
  margin-top: 8px;
  background: rgba(255, 255, 255, 0.13);
  backdrop-filter: blur(60px) saturate(230%) brightness(114%);
  -webkit-backdrop-filter: blur(60px) saturate(230%) brightness(114%);
  border-top:    1.5px solid rgba(255,255,255,0.82);
  border-bottom: 1px   solid rgba(255,255,255,0.18);
  border-left:   1px   solid rgba(255,255,255,0.35);
  border-right:  1px   solid rgba(255,255,255,0.35);
  box-shadow: 0 16px 48px rgba(8,28,50,0.2);
  border-radius: 28px;
  padding: 10px;
  overflow: hidden;
}

.mobile-menu a {
  font-family: 'Playfair Display', Georgia, serif;
  font-style: italic;
  font-size: 17px;
  font-weight: 400;
  color: rgba(255, 255, 255, 0.92);
  text-decoration: none;
  padding: 13px 22px;
  border-radius: 18px;
  transition: background 0.2s;
}

.mobile-menu a:hover { background: rgba(255,255,255,0.1); }
.mobile-menu.open { display: flex; }

/* ── Responsive ── */
@media (max-width: 720px) {
  .header-outer { width: calc(100% - 20px); padding-top: 16px; }
  .logo-name { display: none; }
  nav { display: none; }
  .cta-btn { display: none; }
  .burger { display: flex; padding: 10px 8px; }
  .burger span { width: 22px; height: 2px; }
}
</style>
