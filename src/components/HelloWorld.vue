<template>
  <div class="min-h-screen bg-black text-white font-serif overflow-hidden">

    <!-- 🎵 MUSIC BUTTON -->
    <div class="fixed top-4 right-4 z-50">
      <audio ref="audioRef" src="/music.mp3" loop preload="auto"></audio>

      <button
        @click="toggleMusic"
        class="w-12 h-12 rounded-full bg-black/40 border border-[#D4AF37]/50 backdrop-blur-md flex items-center justify-center hover:scale-110 transition duration-300"
      >
        <!-- PLAY -->
        <svg
          v-if="!isPlaying"
          class="w-5 h-5 text-[#D4AF37] ml-1"
          fill="currentColor"
          viewBox="0 0 24 24"
        >
          <path d="M8 5v14l11-7z"></path>
        </svg>

        <!-- PAUSE -->
        <svg
          v-else
          class="w-5 h-5 text-[#D4AF37]"
          fill="currentColor"
          viewBox="0 0 24 24"
        >
          <path d="M6 5h4v14H6zm8 0h4v14h-4z"></path>
        </svg>
      </button>
    </div>

    <!-- HERO SECTION -->
    <section class="relative min-h-screen">

      <!-- BACKGROUND -->
      <img
        src="/hero.jpg"
        class="absolute inset-0 w-full h-full object-cover object-top"
      />

      <!-- OVERLAY -->
      <div class="absolute inset-0 bg-gradient-to-b from-black/80 via-black/40 to-black/90"></div>

      <!-- FLOATING LANTERNS -->
      <div class="absolute inset-0 overflow-hidden pointer-events-none z-10">
        <div
          v-for="i in 20"
          :key="i"
          class="absolute"
          :style="getLanternStyle(i)"
        >
          <img
            src="/lalten.jpg"
            class="w-12 opacity-70 animate-float-slow"
          />
        </div>
      </div>

      <!-- HERO CONTENT -->
      <div class="relative z-20 flex flex-col items-center justify-center min-h-screen text-center px-4 fade-up">

        <p class="tracking-[8px] uppercase text-sm md:text-lg opacity-80 mb-4">
          Together With Their Families
        </p>

        <h1 class="text-5xl sm:text-6xl md:text-8xl italic leading-tight">
          Shyam

          <span class="block text-pink-500 animate-pulse-slow my-2">
            &
          </span>

          Shraddha
        </h1>

        <p class="mt-6 text-lg md:text-xl opacity-80">
          Are Getting Married
        </p>

        <p class="mt-3 text-xl md:text-2xl text-[#D4AF37]">
          10 May 2026
        </p>

        <!-- RSVP -->
        <a
          href="https://wa.me/919999999999"
          target="_blank"
          class="mt-8 px-8 py-3 rounded-full bg-[#D4AF37] text-black font-semibold hover:scale-105 transition duration-300"
        >
          RSVP NOW
        </a>

      </div>
    </section>

    <!-- INVITATION -->
    <section class="relative z-20 py-20 px-6 text-center fade-up">

      <h2 class="text-4xl md:text-5xl text-[#D4AF37] mb-6">
        You're Invited
      </h2>

      <div class="flex justify-center my-8">
        <div class="w-40 h-[1px] bg-gradient-to-r from-transparent via-[#D4AF37] to-transparent"></div>
      </div>

      <p class="max-w-2xl mx-auto text-white/80 leading-loose">
        Join us as we celebrate love, laughter and a lifetime together 💖
      </p>

    </section>

    <!-- EVENTS -->
    <section class="relative py-20 z-20">

      <!-- LINE -->
      <div class="hidden md:block absolute left-1/2 top-0 w-[2px] h-full bg-gradient-to-b from-[#D4AF37] via-white/20 to-[#D4AF37]"></div>

      <div class="space-y-10 md:space-y-24">

        <!-- HALDI -->
        <div class="flex md:justify-start justify-center px-4 fade-up">
          <div class="w-full md:w-1/2 md:pr-12 text-center md:text-right">
            <div class="event-card">
              <h3>Haldi Ceremony</h3>
              <p>08 May 2026</p>
              <span>09:00 AM</span>
            </div>
          </div>
        </div>

        <!-- SANGEET -->
        <div class="flex md:justify-end justify-center px-4 fade-up">
          <div class="w-full md:w-1/2 md:pl-12 text-center md:text-left">
            <div class="event-card">
              <h3>Sangeet Night</h3>
              <p>09 May 2026</p>
              <span>08:00 PM</span>
            </div>
          </div>
        </div>

        <!-- WEDDING -->
        <div class="flex md:justify-start justify-center px-4 fade-up">
          <div class="w-full md:w-1/2 md:pr-12 text-center md:text-right">
            <div class="event-card">
              <h3>Wedding Ceremony</h3>
              <p>10 May 2026</p>
              <span>08:00 PM</span>
            </div>
          </div>
        </div>

      </div>

    </section>

    <!-- MESSAGE -->
    <section class="relative z-20 py-24 px-6 text-center fade-up">

      <h2 class="text-4xl md:text-5xl text-[#D4AF37] mb-8">
        A Message from the Couple
      </h2>

      <div class="flex justify-center my-8">
        <div class="w-40 h-[1px] bg-gradient-to-r from-transparent via-[#D4AF37] to-transparent"></div>
      </div>

      <p class="max-w-3xl mx-auto text-white/80 leading-loose text-lg">
        With hearts full of love and excitement, we invite you to be a part of our special day as we begin our beautiful journey together.
        Your presence will mean the world to us as we celebrate love, laughter and forever.
      </p>

    </section>

    <!-- GALLERY -->
    <section class="relative z-20 py-20 px-6 fade-up">

      <h2 class="text-center text-4xl md:text-5xl text-[#D4AF37] mb-10">
        Gallery
      </h2>

      <div class="grid grid-cols-2 md:grid-cols-4 gap-4 max-w-6xl mx-auto">

        <img
          v-for="i in 8"
          :key="i"
          :src="`https://picsum.photos/500/60${i}`"
          loading="lazy"
          class="rounded-2xl object-cover h-60 w-full hover:scale-105 transition duration-500"
        />

      </div>

    </section>

    <!-- RING SECTION -->
    <section class="relative z-20 py-20 px-4 fade-up">

      <div class="max-w-6xl mx-auto relative">

        <img
          src="/ring.jpg"
          class="w-full max-h-[750px] object-contain opacity-80"
        />

        <div class="absolute inset-0 flex items-center justify-center text-center">

          <h1 class="text-4xl sm:text-6xl md:text-8xl italic leading-tight text-white/90">
            Shyam

            <span class="block my-3 text-[#D4AF37]">&</span>

            Shraddha
          </h1>

        </div>

      </div>

    </section>

    <!-- COUNTDOWN -->
    <section class="relative z-20 py-24 text-center fade-up">

      <h2 class="text-4xl md:text-5xl text-[#D4AF37] mb-10">
        The Countdown Begins
      </h2>

      <div class="flex justify-center gap-4 flex-wrap px-4">

        <div class="count-box">
          <span>{{ days }}</span>
          <p>Days</p>
        </div>

        <div class="count-box">
          <span>{{ hours }}</span>
          <p>Hours</p>
        </div>

        <div class="count-box">
          <span>{{ minutes }}</span>
          <p>Minutes</p>
        </div>

        <div class="count-box">
          <span>{{ seconds }}</span>
          <p>Seconds</p>
        </div>

      </div>

    </section>

    <!-- LOCATION -->
    <section class="relative z-20 py-20 px-6 fade-up">

      <h2 class="text-center text-4xl md:text-5xl text-[#D4AF37] mb-10">
        Venue Location
      </h2>

      <iframe
        src="https://www.google.com/maps?q=Mumbai&output=embed"
        class="w-full h-72 rounded-3xl max-w-5xl mx-auto border border-[#D4AF37]/30"
      ></iframe>

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

  days.value = String(
    Math.floor(diff / (1000 * 60 * 60 * 24))
  ).padStart(2, "0");

  hours.value = String(
    Math.floor((diff / (1000 * 60 * 60)) % 24)
  ).padStart(2, "0");

  minutes.value = String(
    Math.floor((diff / (1000 * 60)) % 60)
  ).padStart(2, "0");

  seconds.value = String(
    Math.floor((diff / 1000) % 60)
  ).padStart(2, "0");
};

onMounted(() => {
  updateCountdown();
  interval = setInterval(updateCountdown, 1000);
});

onUnmounted(() => {
  clearInterval(interval);
});

/* 🏮 LANTERN */
const getLanternStyle = (i) => {
  return {
    left: (i * 7) % 100 + "%",
    top: (i * 13) % 120 + "%",
    animationDelay: i + "s",
  };
};
</script>

<style>
html {
  scroll-behavior: smooth;
}

body {
  background: black;
}

/* FLOATING */
@keyframes floatSlow {
  0% {
    transform: translate3d(0, 0, 0);
  }

  100% {
    transform: translate3d(0, -200vh, 0);
  }
}

.animate-float-slow {
  animation: floatSlow 25s linear infinite;
}

/* PULSE */
@keyframes pulseSlow {
  0%,100% {
    transform: scale(1);
  }

  50% {
    transform: scale(1.15);
  }
}

.animate-pulse-slow {
  animation: pulseSlow 3s infinite;
}

/* FADE */
.fade-up {
  animation: fadeUp 1.2s ease;
}

@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(40px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* EVENT CARD */
.event-card {
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(212,175,55,0.4);
  border-radius: 24px;
  padding: 28px;
  backdrop-filter: blur(12px);
  transition: 0.5s;
}

.event-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 0 40px rgba(212,175,55,0.3);
}

.event-card h3 {
  font-size: 28px;
  color: #D4AF37;
  margin-bottom: 12px;
}

.event-card p {
  font-size: 18px;
  margin-bottom: 6px;
}

.event-card span {
  opacity: 0.7;
}

/* COUNTDOWN */
.count-box {
  width: 110px;
  height: 110px;
  border-radius: 24px;
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(212,175,55,0.5);
  backdrop-filter: blur(12px);

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  transition: 0.4s;
}

.count-box:hover {
  transform: translateY(-6px);
  box-shadow: 0 0 30px rgba(212,175,55,0.3);
}

.count-box span {
  font-size: 36px;
  color: #D4AF37;
  font-weight: bold;
}

.count-box p {
  margin-top: 6px;
  opacity: 0.7;
  font-size: 14px;
}
</style>