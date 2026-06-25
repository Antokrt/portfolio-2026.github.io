<template>
  <div class="sky">
    <NuxtRouteAnnouncer />
    <NuxtImg src="/cloud.png" class="cloud-bg" alt="" aria-hidden="true" />
    <NuxtPage />
  </div>
</template>

<style>
*, *::before, *::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html { scroll-behavior: smooth; }

body {
  font-family: 'Inter', sans-serif;
  -webkit-font-smoothing: antialiased;
  background: #1B6CA8;
}

.sky {
  min-height: 100vh;
  background: linear-gradient(
    180deg,
    #1460A0 0%,
    #1E78B8 18%,
    #3A9BC8 40%,
    #6CC5E8 65%,
    #9FD9EF 85%,
    #b8e6f5 100%
  );
  position: relative;
}

.cloud-bg {
  position: fixed;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center center;
  z-index: 0;
  opacity: 0.55;
  pointer-events: none;
  user-select: none;
}
</style>
