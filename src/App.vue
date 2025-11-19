<script setup>
import { ref } from 'vue';

// Animasi teks titik-titik (opsional, biar terlihat hidup)
const loadingText = ref('...');
</script>

<template>
  <div class="maintenance-container">
    <div class="glass-card">
      <div class="icon-wrapper">
        <svg xmlns="http://www.w3.org/2000/svg" width="80" height="80" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="shield-icon">
          <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path>
          <path d="M12 8v4"></path>
          <path d="M12 16h.01"></path>
        </svg>
      </div>
      
      <h1>Maintenance dulss cuy</h1>
      <p class="subtitle">
        Sistem kami sedang melakukan pemeliharaan rutin.<br>
        Silakan kembali lagi dalam beberapa saat :)
      </p>
      
      <div class="status-pill">
        <span class="dot"></span>
        Maintenance in progress{{ loadingText }}
      </div>

      <div class="footer">
        <p>&copy; 2025 Muhammad Fazli M | Sainzlab.</p>
      </div>
    </div>
  </div>
</template>

<style>
/* RESET CSS GLOBAL (PENTING AGAR FULL SCREEN) */
body, html {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background-color: #f0f2f5; /* Warna cadangan jika gambar gagal */
}

#app {
  width: 100%;
  height: 100%;
}
</style>

<style scoped>
/* CSS TAMPILAN UTAMA (DOMINAN PUTIH) */
.maintenance-container {
  min-height: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  /* Background Gradient Cerah */
  background: linear-gradient(135deg, #f0f2f5 0%, #e0e6ed 100%);
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  color: #333; /* Warna teks utama */
  position: fixed;
  top: 0;
  left: 0;
}

/* Kartu Kaca (Glassmorphism) - Sekarang dengan background terang */
.glass-card {
  background: rgba(255, 255, 255, 0.7); /* Lebih transparan ke putih */
  backdrop-filter: blur(20px); /* Blur lebih kuat untuk efek kaca */
  -webkit-backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.9); /* Border lebih terang */
  border-radius: 24px;
  padding: 3rem;
  text-align: center;
  max-width: 480px;
  width: 85%;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1); /* Shadow lebih lembut */
}

/* Ikon */
.icon-wrapper {
  margin-bottom: 1.5rem;
  display: flex;
  justify-content: center;
}

.shield-icon {
  width: 80px;
  height: 80px;
  color: #3b82f6; /* Warna biru cerah */
  background-color: rgba(59, 130, 246, 0.1); /* Background samar untuk ikon */
  border-radius: 50%;
  padding: 10px;
  box-sizing: content-box;
  animation: float 3s ease-in-out infinite;
}

/* Teks */
h1 {
  font-size: 1.8rem;
  margin: 0 0 1rem 0;
  font-weight: 700;
  color: #1a202c; /* Warna teks gelap */
}

.subtitle {
  color: #4a5568; /* Warna abu-abu gelap */
  line-height: 1.6;
  margin-bottom: 2rem;
  font-size: 1rem;
}

/* Status Pill (Tombol Lonjong) */
.status-pill {
  display: inline-flex;
  align-items: center;
  background: rgba(59, 130, 246, 0.1); /* Background biru samar */
  color: #2563eb; /* Warna teks biru gelap */
  padding: 0.6rem 1.2rem;
  border-radius: 50px;
  font-size: 0.9rem;
  font-weight: 500;
  border: 1px solid rgba(59, 130, 246, 0.2);
}

.dot {
  width: 8px;
  height: 8px;
  background-color: #2563eb; /* Warna dot biru */
  border-radius: 50%;
  margin-right: 10px;
  box-shadow: 0 0 10px rgba(37, 99, 235, 0.5);
  animation: pulse 2s infinite;
}

.footer {
  margin-top: 3rem;
  font-size: 0.8rem;
  color: #718096; /* Warna abu-abu footer */
}

/* Animasi */
@keyframes float {
  0% { transform: translateY(0px); }
  50% { transform: translateY(-10px); }
  100% { transform: translateY(0px); }
}

@keyframes pulse {
  0% { opacity: 1; }
  50% { opacity: 0.4; }
  100% { opacity: 1; }
}
</style>