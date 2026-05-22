<template>
  <div class="min-h-screen bg-zinc-900 text-white font-serif">

     <!-- 🎵 MUSIC CONTROL -->
    <div class="fixed top-4 right-4 md:top-8 md:right-8 z-50">
      <audio ref="audioRef" src="/music.mp3" loop preload="auto"></audio>

      <button
        @click="toggleMusic"
        class="w-10 h-10 md:w-12 md:h-12 bg-black/40 backdrop-blur-md border border-primary/50 rounded-full flex items-center justify-center shadow-[0_0_15px_rgba(212,175,55,0.3)] hover:shadow-[0_0_25px_rgba(212,175,55,0.6)] hover:bg-black/60 transition-all group"
      >
        <!-- PLAY -->
        <svg v-if="!isPlaying"
             class="w-4 h-4 md:w-5 md:h-5 text-primary group-hover:text-white ml-1"
             fill="currentColor"
             viewBox="0 0 24 24">
          <path d="M8 5v14l11-7z"></path>
        </svg>

        <!-- PAUSE -->
        <svg v-else
             class="w-4 h-4 md:w-5 md:h-5 text-primary group-hover:text-white"
             fill="currentColor"
             viewBox="0 0 24 24">
          <path d="M6 5h4v14H6zm8 0h4v14h-4z"></path>
        </svg>
      </button>
    </div>

    <!-- 🌌 MAIN CONTAINER -->
    <section class="relative min-h-screen">

      <!-- 🔥 BACKGROUND -->
      <img src="/hero.jpg"
           class="absolute top-0 left-0 w-full h-full object-cover object-top z-0"/>

      <!-- 🌑 DARK OVERLAY -->
      <div class="absolute inset-0 bg-black/40 z-10"></div>

      <!-- 🏮 FLOATING LANTERNS -->
      <div class="absolute inset-0 pointer-events-none overflow-hidden h-[300vh] z-20">
        <div v-for="i in 20"
             :key="i"
             class="absolute"
             :style="getLanternStyle(i)">
          <img src="/lalten.jpg"
               class="w-12 opacity-80 animate-float-slow"/>
        </div>
      </div>

      <!-- 💖 HERO CONTENT -->
      <div class="relative z-20 flex flex-col items-center justify-center min-h-screen text-center px-4">

        <h2 class="text-4xl md:text-6xl tracking-widest uppercase mb-6 opacity-90">
          Unveil the Celebration
        </h2>

        <h1 class="text-6xl md:text-8xl italic leading-tight">
          Shyam
          <span class="block text-pink-500">&</span>
          Shraddha
        </h1>

        <p class="mt-6 text-lg opacity-80">
          Are Getting Married
        </p>

        <p class="mt-2 text-xl">10 May 2026</p>

      </div>

      <!-- 💌 INVITE -->
      <div class="relative z-20 text-center py-16 px-6 bg-black/40 backdrop-blur-md">
        <h2 class="text-3xl md:text-5xl text-gold mb-6">You're Invited</h2>
        <p class="max-w-2xl mx-auto text-white/80">
          Join us as we celebrate love, laughter and a lifetime together 💖
        </p>
      </div>

      <!-- 🎬 EVENTS -->
      <div class="relative z-20 py-24 overflow-hidden">

  <!-- Curved SVG Path -->
  <div class="absolute inset-0 flex justify-center pointer-events-none">

    <svg
      class="h-full w-[300px] md:w-[400px]"
      viewBox="0 0 100 1000"
      preserveAspectRatio="none"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >

      <!-- Dotted Background Path -->
      <path
        d="M 50,20 
           C 90,80 90,140 50,200 
           C 10,260 10,320 50,380 
           C 90,440 90,500 50,560 
           C 10,620 10,680 50,740 
           C 90,800 90,860 50,920"
        stroke="#d6c2a8"
        stroke-width="2"
        stroke-dasharray="6 6"
        fill="none"
      />

      <!-- Golden Animated Path -->
      <path
        d="M 50,20 
           C 90,80 90,140 50,200 
           C 10,260 10,320 50,380 
           C 90,440 90,500 50,560 
           C 10,620 10,680 50,740 
           C 90,800 90,860 50,920"
        stroke="url(#goldGradient)"
        stroke-width="4"
        stroke-linecap="round"
        fill="none"
        pathLength="1"
        stroke-dasharray="0.25 1"
      />

      <!-- Gradient -->
      <defs>
        <linearGradient
          id="goldGradient"
          x1="0"
          y1="0"
          x2="0"
          y2="1000"
          gradientUnits="userSpaceOnUse"
        >
          <stop stop-color="#D4AF37" />
          <stop offset="0.5" stop-color="#F3E5AB" />
          <stop offset="1" stop-color="#D4AF37" />
        </linearGradient>
      </defs>

    </svg>
  </div>

  <!-- Timeline Content -->
  <div class="relative z-20 space-y-28">

    <!-- Haldi -->
    <div class="flex justify-start items-center relative">

      <!-- Floating Circle -->
      <div class="absolute left-1/2 -translate-x-1/2 z-30">
        <div class="w-14 h-14 rounded-full border-4 border-[#D4AF37] bg-white shadow-xl flex items-center justify-center text-2xl">
          🌼
        </div>
      </div>

      <div class="w-1/2 pr-12 text-right">
        <div class="event-card bg-white/10 backdrop-blur-md p-6 rounded-3xl border border-white/20 shadow-xl">
          <h3 class="text-2xl font-bold text-[#D4AF37] mb-2">
            Haldi
          </h3>
          <p class="text-white/80">
            08 May 2026
          </p>
          <span class="text-sm text-white/60">
            9:00 AM
          </span>
        </div>
      </div>

    </div>

    <!-- Sangeet -->
    <div class="flex justify-end items-center relative">

      <!-- Floating Circle -->
      <div class="absolute left-1/2 -translate-x-1/2 z-30">
        <div class="w-14 h-14 rounded-full border-4 border-[#D4AF37] bg-white shadow-xl flex items-center justify-center text-2xl">
          🎵
        </div>
      </div>

      <div class="w-1/2 pl-12 text-left">
        <div class="event-card bg-white/10 backdrop-blur-md p-6 rounded-3xl border border-white/20 shadow-xl">
          <h3 class="text-2xl font-bold text-[#D4AF37] mb-2">
            Sangeet
          </h3>
          <p class="text-white/80">
            09 May 2026
          </p>
          <span class="text-sm text-white/60">
            8:00 PM
          </span>
        </div>
      </div>

    </div>

    <!-- Wedding -->
    <div class="flex justify-start items-center relative">

      <!-- Floating Circle -->
      <div class="absolute left-1/2 -translate-x-1/2 z-30">
        <div class="w-14 h-14 rounded-full border-4 border-[#D4AF37] bg-white shadow-xl flex items-center justify-center text-2xl">
          💍
        </div>
      </div>

      <div class="w-1/2 pr-12 text-right">
        <div class="event-card bg-white/10 backdrop-blur-md p-6 rounded-3xl border border-white/20 shadow-xl">
          <h3 class="text-2xl font-bold text-[#D4AF37] mb-2">
            Wedding
          </h3>
          <p class="text-white/80">
            10 May 2026
          </p>
          <span class="text-sm text-white/60">
            8:00 PM
          </span>
        </div>
      </div>

    </div>

  </div>

</div>

      <!-- 💌 MESSAGE -->
      <div class="relative z-20 text-center py-24 px-6">
        <h2 class="text-4xl text-gold mb-6">A Message from the Couple</h2>
        <p class="max-w-3xl mx-auto text-white/80 leading-loose">
          With hearts full of love and excitement, we invite you to be a part of our special day as we begin our beautiful journey together. Your presence will mean the world to us as we celebrate love, laughter, and a lifetime of togetherness. Join us on May 9th and 10th at Madhuvan Garden to bless us as we step into this new chapter of our lives.
        </p>
      </div>

      
      <!-- 🖼️ GALLERY -->
      <div class="relative z-20 py-20 px-6">
        <h2 class="text-center text-4xl text-gold mb-10">Gallery</h2>

        <div class="grid grid-cols-2 md:grid-cols-4 gap-4 max-w-6xl mx-auto">
          <img v-for="i in 6"
               :key="i"
               :src="`https://picsum.photos/400/40${i}`"
               class="rounded-xl hover:scale-110 transition duration-500"/>
        </div>
      </div>

      

      <!-- 💍 YOUR ADDED SECTION (ABOVE COUNTDOWN) -->
      <div class="relative z-20 py-16 md:py-20 px-4 text-center">
  <div class="mx-auto max-w-[1200px] w-full">
    
    <div class="relative w-full">

      <!-- RING IMAGE -->
      <img 
        src="/ring.jpg"
        class="w-full h-auto max-h-[500px] md:max-h-[650px] lg:max-h-[750px] object-contain mx-auto opacity-80"
      />

      <!-- NAMES -->
      <div class="absolute inset-0 flex flex-col items-center justify-center text-center px-4">
        <h1 class="text-3xl sm:text-5xl md:text-7xl lg:text-8xl font-serif italic text-white/90 drop-shadow-md leading-tight">
          Shyam
          <span class="block text-xl sm:text-3xl md:text-5xl lg:text-6xl my-2 md:my-4">&</span>
          Shraddha
        </h1>
      </div>

    </div>

  </div>
</div>

      <!-- ⏳ COUNTDOWN -->
<div class="relative z-20 text-center py-24">
  <h2 class="text-4xl text-gold mb-6">The countdown begins</h2>

  <div class="text-5xl tracking-widest">
    {{ days }} : {{ hours }} : {{ minutes }} : {{ seconds }}
  </div>
</div>

      <!-- 📍 LOCATION -->
      <div class="relative z-20 py-16 px-6">
        <iframe
          src="https://www.google.com/maps?q=Mumbai&output=embed"
          class="w-full h-64 rounded-xl max-w-4xl mx-auto"
        ></iframe>
      </div>

    </section>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

/* 🎵 MUSIC */
const audioRef = ref(null);
const isPlaying = ref(false);

const toggleMusic = () => {
  if (!audioRef.value) return;

  if (isPlaying.value) {
    audioRef.value.pause();
  } else {
    audioRef.value.play();
  }

  isPlaying.value = !isPlaying.value;
};

onMounted(() => {
  if (audioRef.value) {
    audioRef.value.play()
      .then(() => isPlaying.value = true)
      .catch(() => isPlaying.value = false);
  }

  updateCountdown();
  interval = setInterval(updateCountdown, 1000);
});

/* ⏳ COUNTDOWN */
const days = ref("00");
const hours = ref("00");
const minutes = ref("00");
const seconds = ref("00");

let interval;

const updateCountdown = () => {
  const weddingDate = new Date("May 10, 2026 00:00:00").getTime();
  const now = new Date().getTime();
  const diff = weddingDate - now;

  if (diff <= 0) {
    clearInterval(interval);
    return;
  }

  days.value = String(Math.floor(diff / (1000 * 60 * 60 * 24))).padStart(2, "0");
  hours.value = String(Math.floor((diff / (1000 * 60 * 60)) % 24)).padStart(2, "0");
  minutes.value = String(Math.floor((diff / (1000 * 60)) % 60)).padStart(2, "0");
  seconds.value = String(Math.floor((diff / 1000) % 60)).padStart(2, "0");
};

onUnmounted(() => {
  clearInterval(interval);
});

/* 🏮 LANTERN */
const getLanternStyle = (i) => {
  return {
    left: (i * 7) % 100 + "%",
    top: (i * 13) % 200 + "%",
    animationDelay: i + "s"
  };
};
</script>

<style>
.text-gold {
  color: #D4AF37;
}

@keyframes floatSlow {
  0% { transform: translateY(0); }
  100% { transform: translateY(-200vh); }
}

.animate-float-slow {
  animation: floatSlow 25s linear infinite;
}

.event-card {
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(212,175,55,0.5);
  padding: 20px;
  border-radius: 16px;
  backdrop-filter: blur(10px);
  transition: 0.4s;
}

.event-card:hover {
  transform: scale(1.05);
  box-shadow: 0 0 30px rgba(212,175,55,0.6);
}
</style>

<style>
.text-gold {
  color: #D4AF37;
}

@keyframes floatSlow {
  0% { transform: translateY(0); }
  100% { transform: translateY(-200vh); }
}

.animate-float-slow {
  animation: floatSlow 25s linear infinite;
}

.event-card {
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(212,175,55,0.5);
  padding: 20px;
  border-radius: 16px;
  backdrop-filter: blur(10px);
  transition: 0.4s;
}

.event-card:hover {
  transform: scale(1.05);
  box-shadow: 0 0 30px rgba(212,175,55,0.6);
}

.event-card h3 {
  font-size: 24px;
  color: #D4AF37;
}

.event-card span {
  opacity: 0.7;
  font-size: 14px;
}
</style>