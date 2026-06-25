<template>
  <div class="marquee-outer" aria-hidden="true">
    <div class="marquee-track">
      <ul class="marquee-list" v-for="n in 2" :key="n">
        <li v-for="client in clients" :key="`${n}-${client.name}`" class="client-item">
          <span class="client-icon" v-html="client.icon"></span>
          <span class="client-name">{{ client.name.charAt(0).toUpperCase() + client.name.slice(1) }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
const clients = [
  {
    name: 'responsive',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none">
      <rect x="2" y="5" width="20" height="14" rx="2" stroke="#cccccc" stroke-width="1.5"/>
      <path d="M8 19v2M16 19v2M5 21h14" stroke="#cccccc" stroke-width="1.5" stroke-linecap="round"/>
    </svg>`
  },
  {
    name: 'référencement',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none">
      <circle cx="11" cy="11" r="7" stroke="#cccccc" stroke-width="1.5"/>
      <path d="M16.5 16.5L21 21" stroke="#cccccc" stroke-width="1.5" stroke-linecap="round"/>
      <path d="M8 11h6M11 8v6" stroke="#cccccc" stroke-width="1.5" stroke-linecap="round"/>
    </svg>`
  },
  {
    name: 'performance',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none">
      <path d="M13 2L4.5 13.5H11L10 22L19.5 10.5H13L13 2Z"
            stroke="#cccccc" stroke-width="1.5" stroke-linejoin="round" fill="none"/>
    </svg>`
  },
  {
    name: 'sur-mesure',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none">
      <path d="M12 2l2.5 7H22l-6 4.5 2.5 7L12 17l-6.5 3.5L8 13.5 2 9h7.5L12 2Z"
            stroke="#cccccc" stroke-width="1.5" fill="none" stroke-linejoin="round"/>
    </svg>`
  },
  {
    name: 'conversion',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none">
      <path d="M3 17l4-8 4 5 3-3 4 6" stroke="#cccccc" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>`
  },
  {
    name: 'mobile-first',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none">
      <rect x="7" y="2" width="10" height="20" rx="2" stroke="#cccccc" stroke-width="1.5"/>
      <circle cx="12" cy="18" r="1" fill="#cccccc"/>
    </svg>`
  },
  {
    name: 'accessibilité',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none">
      <circle cx="12" cy="5" r="2" stroke="#cccccc" stroke-width="1.5"/>
      <path d="M12 8v5M8 10l4 3 4-3M10 22l2-5 2 5" stroke="#cccccc" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>`
  },
  {
    name: 'optimisation',
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none">
      <circle cx="12" cy="12" r="9" stroke="#cccccc" stroke-width="1.5"/>
      <path d="M12 7v5l3 3" stroke="#cccccc" stroke-width="1.5" stroke-linecap="round"/>
    </svg>`
  },
]
</script>

<style scoped>
.marquee-outer {
  width: 100%;
  background: #ffffff;
  overflow: hidden;
  padding: 20px 0;
  border-top: 1px solid #f0f0f0;
  border-bottom: 1px solid #f0f0f0;
}

.marquee-track {
  display: flex;
  width: max-content;
  animation: marquee 45s linear infinite;
}

.marquee-list {
  display: flex;
  align-items: center;
  gap: 60px;
  padding: 0 30px;
  list-style: none;
}

.client-item {
  display: flex;
  align-items: center;
  gap: 10px;
  white-space: nowrap;
  flex-shrink: 0;
}

.client-icon {
  display: flex;
  align-items: center;
  flex-shrink: 0;
}

.client-name {
  font-family: 'Playfair Display', Georgia, serif;
  font-style: italic;
  font-size: 16px;
  font-weight: 400;
  color: #aaaaaa;
  letter-spacing: 0.01em;
}

@keyframes marquee {
  from { transform: translateX(0); }
  to   { transform: translateX(-50%); }
}
</style>
