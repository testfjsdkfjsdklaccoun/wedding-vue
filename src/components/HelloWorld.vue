<template>
  <div class="min-h-screen bg-zinc-900 text-white font-serif">

    <!-- 🌌 MAIN CONTAINER -->
    <section class="relative min-h-screen">

      <!-- 🔥 BACKGROUND -->
      <img src="/hero.jpg"
           class="absolute top-0 left-0 w-full h-full object-cover object-top z-0"/>

      <!-- 🌑 DARK OVERLAY (FIXED) -->
      <div class="absolute inset-0 bg-black/40 z-10"></div>

      <!-- 🏮 FLOATING LANTERNS -->
      <div class="absolute inset-0 pointer-events-none overflow-hidden h-[300vh] z-20">
        <div v-for="i in 20"
             :key="i"
             class="absolute"
             :style="getLanternStyle(i)">
          <img src="https://cdn-icons-png.flaticon.com/512/869/869636.png"
               class="w-12 opacity-80 animate-float-slow"/>
        </div>
      </div>

      <!-- 💖 HERO CONTENT -->
      <div class="relative z-20 flex flex-col items-center justify-center min-h-screen text-center px-4">

        <h2 class="text-4xl md:text-6xl tracking-widest uppercase mb-6 opacity-90">
          Unveil the Celebration
        </h2>

        <h1 class="text-6xl md:text-8xl italic leading-tight">
          Tanvir
          <span class="block text-pink-500">&</span>
          Partner
        </h1>

        <p class="mt-6 text-lg opacity-80">
          Are Getting Married
        </p>

        <p class="mt-2 text-xl">12 December 2026</p>

      </div>

      <!-- 💌 INVITE -->
      <div class="relative z-20 text-center py-16 px-6 bg-black/40 backdrop-blur-md">
        <h2 class="text-3xl md:text-5xl text-gold mb-6">You're Invited</h2>
        <p class="max-w-2xl mx-auto text-white/80">
          Join us as we celebrate love, laughter and a lifetime together 💖
        </p>
      </div>

      <!-- 🎬 EVENTS -->
      <div class="relative z-20 py-24">

        <div class="absolute left-1/2 top-0 w-[2px] h-full bg-gradient-to-b from-gold via-white/30 to-gold"></div>

        <div class="space-y-24">

          <div class="flex justify-start">
            <div class="w-1/2 pr-10 text-right">
              <div class="event-card">
                <h3>Haldi</h3>
                <p>20 April 2026</p>
                <span>9:00 AM</span>
              </div>
            </div>
          </div>

          <div class="flex justify-end">
            <div class="w-1/2 pl-10 text-left">
              <div class="event-card">
                <h3>Sangeet</h3>
                <p>19 April 2026</p>
                <span>8:00 PM</span>
              </div>
            </div>
          </div>

          <div class="flex justify-start">
            <div class="w-1/2 pr-10 text-right">
              <div class="event-card">
                <h3>Wedding</h3>
                <p>20 April 2026</p>
                <span>8:00 PM</span>
              </div>
            </div>
          </div>

        </div>
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

      <!-- 💌 MESSAGE -->
      <div class="relative z-20 text-center py-24 px-6">
        <h2 class="text-4xl text-gold mb-6">A Message from the Couple</h2>
        <p class="max-w-3xl mx-auto text-white/80 leading-loose">
          With hearts full of love and excitement, we invite you to be a part of our special day.
        </p>
      </div>

      <!-- ⏳ COUNTDOWN -->
      <div class="relative z-20 text-center py-24">
        <h2 class="text-4xl text-gold mb-6">The countdown begins</h2>

        <div class="text-5xl tracking-widest">
          10 : 05 : 40 : 59
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

/* ✨ FLOAT */
@keyframes floatSlow {
  0% { transform: translateY(0); }
  100% { transform: translateY(-200vh); }
}

.animate-float-slow {
  animation: floatSlow 25s linear infinite;
}

/* 🎬 EVENT CARD */
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