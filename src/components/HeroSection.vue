<script setup>
import { onMounted, ref } from "vue";

const props = defineProps({
  scrollToSection: Function,
});

const canvasRef = ref(null);
const typedText = ref("");
const typedSubtitle = ref("");
const typedTitle = ref("");
const showCursor = ref(true);
const showTitleCursor = ref(true);

onMounted(() => {
  // Matrix Rain Effect
  const canvas = canvasRef.value;
  if (!canvas) return;

  const ctx = canvas.getContext("2d");
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;

  const characters =
    "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789@#$%^&*(){}[]<>/\\|~";
  const fontSize = 14;
  const columns = canvas.width / fontSize;
  const drops = Array(Math.floor(columns)).fill(1);

  function draw() {
    ctx.fillStyle = "rgba(0, 0, 0, 0.05)";
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    ctx.fillStyle = "#00ff41";
    ctx.font = fontSize + "px monospace";

    for (let i = 0; i < drops.length; i++) {
      const text = characters.charAt(
        Math.floor(Math.random() * characters.length)
      );
      ctx.fillText(text, i * fontSize, drops[i] * fontSize);

      if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
        drops[i] = 0;
      }
      drops[i]++;
    }
  }

  const interval = setInterval(draw, 33);

  const handleResize = () => {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  };

  window.addEventListener("resize", handleResize);

  // Typing Animation
  const fullText = "> Capture the Flag 2026_";
  const titleText = "CSC_CYBERWAR";
  const subtitleText = "[ CSAD_2026 ]";
  let charIndex = 0;
  let titleIndex = 0;
  let subtitleIndex = 0;

  const typeText = () => {
    if (charIndex < fullText.length) {
      typedText.value = fullText.substring(0, charIndex + 1);
      charIndex++;
      setTimeout(typeText, 100);
    } else {
      // Start typing title after intro text is done
      setTimeout(typeTitle, 400);
    }
  };

  const typeTitle = () => {
    if (titleIndex < titleText.length) {
      typedTitle.value = titleText.substring(0, titleIndex + 1);
      titleIndex++;
      setTimeout(typeTitle, 120);
    } else {
      // Hide title cursor after done
      setTimeout(() => {
        showTitleCursor.value = false;
        // Start typing subtitle
        setTimeout(typeSubtitle, 300);
      }, 500);
    }
  };

  const typeSubtitle = () => {
    if (subtitleIndex < subtitleText.length) {
      typedSubtitle.value = subtitleText.substring(0, subtitleIndex + 1);
      subtitleIndex++;
      setTimeout(typeSubtitle, 80);
    }
  };

  // Cursor blink
  const cursorInterval = setInterval(() => {
    showCursor.value = !showCursor.value;
  }, 500);

  const titleCursorInterval = setInterval(() => {
    showTitleCursor.value = !showTitleCursor.value;
  }, 500);

  // Start typing after a short delay
  setTimeout(typeText, 500);

  return () => {
    clearInterval(interval);
    clearInterval(cursorInterval);
    clearInterval(titleCursorInterval);
    window.removeEventListener("resize", handleResize);
  };
});
</script>

<template>
  <section
    class="relative min-h-screen flex items-center justify-center bg-gradient-to-br from-black via-cyber-dark to-darker-bg overflow-hidden pt-24 sm:pt-20 md:pt-0"
  >
    <!-- Matrix Rain Canvas -->
    <canvas ref="canvasRef" class="absolute inset-0 opacity-20"></canvas>

    <!-- Animated Grid Background -->
    <div
      class="absolute inset-0 opacity-10"
      style="
        background-image: linear-gradient(
            rgba(0, 255, 65, 0.1) 1px,
            transparent 1px
          ),
          linear-gradient(90deg, rgba(255, 0, 0, 0.1) 1px, transparent 1px);
        background-size: 50px 50px;
      "
    ></div>

    <!-- Scan Line Effect -->
    <div class="absolute inset-0 opacity-20 pointer-events-none">
      <div
        class="h-1 w-full bg-gradient-to-r from-transparent via-cyber-blue to-transparent animate-scan"
      ></div>
    </div>

    <!-- Floating Circuit Elements -->
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
      <div
        class="absolute top-20 left-10 w-16 h-16 border-2 border-cyber-green opacity-30 animate-float"
      ></div>
      <div
        class="absolute top-40 right-20 w-20 h-20 border-2 border-cyber-blue opacity-20 animate-float"
        style="animation-delay: 0.5s"
      ></div>
      <div
        class="absolute bottom-32 left-1/4 w-12 h-12 border-2 border-cyber-purple opacity-25 animate-float"
        style="animation-delay: 1s"
      ></div>
      <div
        class="absolute bottom-20 right-1/3 w-24 h-24 border-2 border-cyber-red opacity-15 animate-float"
        style="animation-delay: 1.5s"
      ></div>
    </div>

    <div class="relative z-10 text-center px-4 py-8 sm:px-6">
      <!-- Typing Animation Text -->
      <div class="min-h-[2rem] mb-2 sm:mb-3">
        <p
          class="text-xs sm:text-sm md:text-base lg:text-lg text-cyber-green uppercase tracking-[0.2em] sm:tracking-[0.3em] font-mono"
        >
          {{ typedText
          }}<span
            v-if="showCursor && typedText.length > 0"
            class="animate-pulse"
            >|</span
          >
        </p>
      </div>

      <!-- Glitch Title with Typing Animation -->
      <div
        class="relative inline-block mb-3 sm:mb-4 min-h-[4rem] sm:min-h-[5rem] md:min-h-[6rem] lg:min-h-[7rem]"
      >
        <h1
          class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl xl:text-8xl font-bold text-white tracking-wider leading-tight relative z-10 font-mono"
          style="
            text-shadow: 0 0 10px rgba(255, 0, 0, 0.8),
              0 0 20px rgba(255, 0, 0, 0.6), 0 0 30px rgba(255, 0, 0, 0.4),
              2px 2px 0px rgba(0, 255, 65, 0.3),
              -2px -2px 0px rgba(0, 217, 255, 0.3);
          "
        >
          {{ typedTitle
          }}<span
            v-if="showTitleCursor && typedTitle.length < 12"
            class="animate-pulse text-cyber-green"
            >|</span
          >
        </h1>
        <h1
          v-if="typedTitle.length > 0"
          class="absolute top-0 left-0 text-4xl sm:text-5xl md:text-6xl lg:text-7xl xl:text-8xl font-bold text-cyber-red tracking-wider leading-tight opacity-70 animate-glitch font-mono"
          style="text-shadow: 2px 0 0 rgba(255, 0, 0, 0.7)"
        >
          {{ typedTitle }}
        </h1>
        <h1
          v-if="typedTitle.length > 0"
          class="absolute top-0 left-0 text-4xl sm:text-5xl md:text-6xl lg:text-7xl xl:text-8xl font-bold text-cyber-blue tracking-wider leading-tight opacity-70 animate-glitch font-mono"
          style="
            animation-delay: 0.2s;
            text-shadow: -2px 0 0 rgba(0, 217, 255, 0.7);
          "
        >
          {{ typedTitle }}
        </h1>
      </div>

      <!-- Typing Animation Subtitle -->
      <div class="min-h-[2rem] mb-8 sm:mb-12">
        <p
          class="text-sm sm:text-base md:text-lg text-cyber-blue tracking-widest font-mono"
        >
          {{ typedSubtitle
          }}<span
            v-if="
              showCursor &&
              typedSubtitle.length > 0 &&
              typedSubtitle.length < 13
            "
            class="animate-pulse"
            >|</span
          >
        </p>
      </div>

      <div
        class="flex flex-col sm:flex-row gap-4 sm:gap-6 justify-center items-stretch sm:items-center max-w-md sm:max-w-none mx-auto"
      >
        <button
          class="group relative border-2 border-cyber-red text-cyber-red px-8 sm:px-10 md:px-12 py-4 text-base sm:text-lg md:text-xl uppercase tracking-widest hover:bg-cyber-red hover:text-black transition-all overflow-hidden animate-pulse-glow"
        >
          <span class="relative z-10">Join the Battle</span>
          <div
            class="absolute inset-0 bg-cyber-red transform scale-x-0 group-hover:scale-x-100 transition-transform origin-left"
          ></div>
          <span class="relative z-10 group-hover:text-black">&gt;&gt;</span>
        </button>
        <button
          @click="scrollToSection('rules')"
          class="group relative border-2 border-cyber-blue text-cyber-blue px-8 sm:px-10 md:px-12 py-4 text-base sm:text-lg md:text-xl uppercase tracking-widest hover:bg-cyber-blue hover:text-black transition-all overflow-hidden"
        >
          <span class="relative z-10">Read Rules</span>
          <div
            class="absolute inset-0 bg-cyber-blue transform scale-x-0 group-hover:scale-x-100 transition-transform origin-left"
          ></div>
        </button>
      </div>
    </div>

    <!-- Scroll Navigation -->
    <div
      class="absolute bottom-6 sm:bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce"
    >
      <button
        @click="scrollToSection('bounty')"
        class="flex flex-col items-center gap-2 text-cyber-green hover:text-cyber-blue transition-colors group"
      >
        <span class="text-xs uppercase tracking-widest"
          >&lt; Scroll Down &gt;</span
        >
        <svg
          class="w-6 h-6 group-hover:animate-pulse"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M19 14l-7 7m0 0l-7-7m7 7V3"
          ></path>
        </svg>
      </button>
    </div>
  </section>
</template>
