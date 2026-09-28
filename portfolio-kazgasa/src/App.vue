<template>
  <div class="min-h-screen bg-neutral-50 text-neutral-900 font-sans selection:bg-neutral-200">
    <header class="sticky top-0 z-50 backdrop-blur-md bg-white/70 border-b border-neutral-200/80 navbar">
      <div class="max-w-6xl mx-auto px-4 h-16 flex items-center justify-between">
        <a href="#" class="font-mono text-sm tracking-widest uppercase hover:opacity-70 transition-opacity">
          A. Siitova // Portfolio
        </a>
        <nav class="flex space-x-8 text-xs font-mono tracking-wider uppercase">
          <a href="#about" class="hover:text-neutral-500 transition-colors">О себе</a>
          <a href="#projects" class="hover:text-neutral-500 transition-colors">Чертежи и макеты</a>
          <a href="#certificates" class="hover:text-neutral-500 transition-colors">Достижения</a>
          <a href="#contact" class="hover:text-neutral-500 transition-colors">Контакты</a>
        </nav>
      </div>
    </header>

    <main class="max-w-6xl mx-auto px-4 py-12 space-y-32">
      <section id="about" class="py-12 md:py-20 max-w-3xl">
        <p class="font-mono text-xs text-neutral-500 uppercase tracking-widest mb-4">Архитектура & Проектирование</p>
        <h1 class="text-4xl md:text-6xl font-light tracking-tight mb-6 text-neutral-900 leading-none">
          Алтынай Сиитова
        </h1>
        <p class="text-neutral-600 text-lg md:text-xl font-light leading-relaxed mb-8">
          Студентка Казахской головной архитектурно-строительной академии (<span class="font-normal text-neutral-800">КазГАСА</span>). 
          Сочетаю академическую точность архитектурного проектирования с активной организационной деятельностью в международных проектах.
        </p>
        <div class="flex flex-wrap gap-3">
          <span class="px-3 py-1 bg-white border border-neutral-200 rounded-full text-xs font-mono text-neutral-600">Черчение & Графика</span>
          <span class="px-3 py-1 bg-white border border-neutral-200 rounded-full text-xs font-mono text-neutral-600">Бумажное макетирование</span>
          <span class="px-3 py-1 bg-white border border-neutral-200 rounded-full text-xs font-mono text-neutral-600">Архитектурная композиция</span>
          <span class="px-3 py-1 bg-white border border-neutral-200 rounded-full text-xs font-mono text-neutral-600">Event-Management</span>
        </div>
      </section>

      <section id="projects" class="space-y-8 scroll-mt-20">
        <div class="border-b border-neutral-200 pb-4">
          <h2 class="text-2xl font-light tracking-tight text-neutral-900">Академические проекты и графика</h2>
          <p class="text-xs font-mono text-neutral-500 mt-1">Работы, выполненные в рамках обучения в КазГАСА</p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div v-for="(project, index) in projects" :key="index" class="group bg-white border border-neutral-200/60 overflow-hidden flex flex-col justify-between hover:shadow-sm transition-all duration-300">
            <div class="aspect-3/4 md:aspect-4/5 bg-neutral-100 overflow-hidden relative">
              <img 
                :src="project.image" 
                :alt="project.title"
                class="w-full h-full object-cover grayscale group-hover:grayscale-0 group-hover:scale-105 transition-all duration-500"
                loading="lazy"
              />
            </div>
            <div class="p-6 bg-white border-t border-neutral-100">
              <div class="flex justify-between items-start mb-2">
                <h3 class="text-base font-normal text-neutral-900">{{ project.title }}</h3>
                <span class="text-xs font-mono bg-neutral-100 px-2 py-0.5 rounded text-neutral-600">{{ project.grade }}</span>
              </div>
              <p class="text-sm text-neutral-500 font-light">{{ project.description }}</p>
            </div>
          </div>
        </div>
      </section>

      <section id="certificates" class="space-y-8 scroll-mt-20">
        <div class="border-b border-neutral-200 pb-4">
          <h2 class="text-2xl font-light tracking-tight text-neutral-900">Международный опыт и признание</h2>
          <p class="text-xs font-mono text-neutral-500 mt-1">Участие в глобальных событиях, форумах и спортивных чемпионатах</p>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
          <div v-for="(cert, index) in certificates" :key="index" class="bg-white border border-neutral-200 p-6 flex flex-col justify-between hover:border-neutral-400 transition-colors">
            <div>
              <span class="text-[10px] font-mono tracking-widest text-neutral-400 uppercase block mb-2">{{ cert.date }}</span>
              <h3 class="text-sm font-normal text-neutral-900 mb-2 leading-snug">{{ cert.title }}</h3>
              <p class="text-xs text-neutral-500 font-light mb-4">{{ cert.issuer }}</p>
            </div>
            <div class="pt-4 border-t border-neutral-100 flex items-center justify-between">
              <span class="text-xs font-mono text-neutral-400">Role: {{ cert.role }}</span>
              <a :href="cert.image" target="_blank" class="text-xs font-mono text-neutral-900 underline hover:text-neutral-500 transition-colors">
                View doc
              </a>
            </div>
          </div>
        </div>
      </section>

      <section id="contact" class="scroll-mt-20 max-w-xl pb-20">
        <div class="border-b border-neutral-200 pb-4 mb-8">
          <h2 class="text-2xl font-light tracking-tight text-neutral-900">Связаться</h2>
          <p class="text-xs font-mono text-neutral-500 mt-1">Открыта к академическим проектам, архитектурным конкурсам и коллаборациям</p>
        </div>
        
        <div class="space-y-6 font-mono text-sm">
          <div>
            <span class="text-neutral-400 block text-xs uppercase tracking-wider mb-1">Локация</span>
            <span class="text-neutral-800">Алматы, Казахстан</span>
          </div>
          <div>
            <span class="text-neutral-400 block text-xs uppercase tracking-wider mb-1">Email для связи</span>
            <a href="mailto:siitovaaltyn@gmail.com" class="text-neutral-900 underline hover:text-neutral-500 transition-colors">siitovaaltyn@gmail.com</a>
          </div>
          <div>
            <span class="text-neutral-400 block text-xs uppercase tracking-wider mb-1">Образование</span>
            <span class="text-neutral-800">КазГАСА (Казахская головная архитектурно-строительной академия)</span>
            <br />
            <span class="text-neutral-800">1 курс</span>
          </div>
        </div>
      </section>
    </main>

    <footer class="border-t border-neutral-200 bg-white py-8 text-center text-xs font-mono text-neutral-400">
      <div class="max-w-6xl mx-auto px-4">
        &copy; {{ new Date().getFullYear() }} Алтынай Сиитова. Разработано с использованием Vue & Tailwind.
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const projects = ref([
  {
    title: 'Архитектурные ордера',
    description: 'Академический чертеж классических архитектурных ордеров: Тосканский, Дорический, Ионический, Коринфский. Подробная прорисовка деталей, пропорций и элементов антаблемента.',
    grade: 'Оценка: 88',
    image: '/image_5NTwBu.jpeg'
  },
  {
    title: 'Архитектурные обломы (Профили)',
    description: 'Чертеж основных архитектурных профилей (обломов): пояс, полочка, прямой/обратный четвертной вал, выкружка, гусек, каблучок, астрагал, торус, скоция.',
    grade: 'Оценка: 80',
    image: '/image_AOOS8m.jpeg'
  },
  {
    title: 'Объемно-пространственная пластика',
    description: 'Композиционные упражнения по бумажной пластике. Исследование светотени, сгибов, граней и трансформации плоскости в объемный рельеф.',
    grade: 'Оценка: 85',
    image: '/image__WFN3B.jpeg'
  },
  {
    title: 'Геометрическая цветная композиция',
    description: 'Графический лист, посвященный исследованию изометрии, цветового контраста и оптических иллюзий на основе объемных геометрических модулей.',
    grade: 'Оценка: 80',
    image: '/image_tZ_y8f.jpeg'
  }
])

const certificates = ref([
  {
    title: 'FIBA 3x3 World Tour Almaty 2024',
    issuer: 'The Organizing Committee of the FIBA 3x3 World Tour',
    date: '13-14 Июля 2024',
    role: 'Volunteer / Организация',
    image: '/image_gsbAcf.jpeg'
  },
  {
    title: 'FIS Freestyle Junior World Ski Championships',
    issuer: 'Alpine Skiing, Freestyle, and Snowboard Federation of Almaty',
    date: '7-11 Января 2025',
    role: 'Volunteer Support',
    image: '/vol/Volunteer And Certificate_pages-to-jpg-0001.jpg'
  },
  {
    title: 'FIS Freestyle Ski World Cup (Moguls & Aerials)',
    issuer: 'Kazakhstan Ski Association & Shymbulak Mountain Resort',
    date: '28 Февраля — 2 Марта 2025',
    role: 'Professional Assistance',
    image: '/vol/Volunteer And Certificate_pages-to-jpg-0002.jpg'
  },
  {
    title: 'Global Sparks Showcase (Business & IT)',
    issuer: 'Lancaster University, Oregon State University, NOVA Education',
    date: '5 Ноября 2025',
    role: 'Participant',
    image: '/vol/Volunteer And Certificate_pages-to-jpg-0002.jpg'
  },
  {
    title: 'International Summit «AI for Education»',
    issuer: 'Общественный фонд HOPE (Help Others Pursue Education)',
    date: '21-23 Апреля 2026',
    role: 'Summit Volunteer',
    image: '/vol/Благ Письмо БПSiitova Altynai_page-0001.jpg'
  },
  {
    title: 'Гуманитарная неделя культурно-туристического обмена (II Саммит «Центральная Азия – Китай»)',
    issuer: 'Управление туризма города Алматы (Visit Almaty)',
    date: 'Апрель 2026',
    role: 'Организационная помощь',
    image: '/vol/img7.jpg'
  }
])
</script>

<style scoped>
html {
  scroll-behavior: smooth;
}
</style>