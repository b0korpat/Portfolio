<template>
  <div class="flex bg-gradient-to-b from-gray-950 via-gray-900 to-gray-950 min-h-screen text-gray-200">
    <aside class="rounded-xl fixed left-0 top-0 h-screen w-64 bg-gray-900/95 backdrop-blur-sm border-r border-purple-800/30 flex flex-col z-50 transform transition-transform duration-300 2xl:translate-x-0"
           :class="{ '-translate-x-full': !sidebarOpen }">
      <div class="p-6 border-b border-purple-800/30">
        <h1 class="text-2xl font-bold text-white">
          <span class="text-purple-400">K.</span>Patrik
        </h1>
      </div>

      <nav class="flex-1 p-4 overflow-y-auto">
        <div class="space-y-2">
          <NavLink
              v-for="link in navLinks"
              :key="link.href"
              :href="link.href"
              :icon="link.icon"
              :label="link.label"
              :isActive="activeSection === link.id"
              @click="toggleSidebar"
          />
        </div>
      </nav>

      <div class="p-6 border-t border-purple-800/30">
        <div class="flex space-x-4">
          <SocialIcon href="https://github.com/b0korpat" icon="bi-github" />
          <SocialIcon href="www.linkedin.com/in/patrik-kordás-b8479a20a" icon="bi-linkedin" />
          <SocialIcon href="https://www.facebook.com/kordas.patrik/" icon="bi-facebook" />
        </div>
      </div>
    </aside>

    <button
        @click="toggleSidebar"
        class="z-[999] 2xl:hidden fixed top-4 left-0 flex items-center justify-center w-10 h-10 bg-gray-800/80 text-white rounded-full backdrop-blur-sm border border-purple-800/30 shadow-lg hover:shadow-purple-500/20 transition-all duration-[0.3s] ease-in-out transform"
        :style="{
          transform: sidebarOpen
            ? `translateX(270px) rotate(90deg) scale(1.1)`
            : 'translateX(1rem) rotate(0) scale(1)'
        }">
      <i class="bi transition-all duration-[0.3s] transform"
         :class="[
       sidebarOpen ? 'bi-x-lg rotate-180 scale-110' : 'bi-list rotate-0',
       'text-lg'
     ]">
      </i>
    </button>

    <main class="flex-1 ml-0 bg-gradient-to-b from-gray-900/70 via-gray-800/50 to-gray-900/70 relative overflow-hidden">

      <div class="absolute inset-0 overflow-hidden pointer-events-none z-0">
        <div class="absolute top-[5%] right-[10%] w-[800px] h-[800px] rounded-full bg-purple-700/10 blur-[100px] animate-random-move"></div>

        <div class="absolute bottom-[20%] left-[10%] w-[600px] h-[600px] rounded-full bg-fuchsia-700/10 blur-[80px] animate-random-move-delayed"></div>

        <div class="absolute top-[50%] left-[45%] w-[400px] h-[400px] rounded-full bg-purple-600/10 blur-[60px] animate-random-move-alternate"></div>

        <div class="absolute top-[30%] left-[25%] w-[200px] h-[200px] rounded-full bg-fuchsia-500/10 blur-[40px] animate-random-move"></div>
        <div class="absolute top-[70%] right-[20%] w-[300px] h-[300px] rounded-full bg-purple-500/10 blur-[50px] animate-random-move-delayed"></div>

        <div class="absolute top-[85%] left-[60%] w-[250px] h-[250px] rounded-full bg-purple-800/10 blur-[45px] animate-random-move"></div>
        <div class="absolute top-[15%] left-[40%] w-[350px] h-[350px] rounded-full bg-fuchsia-600/10 blur-[55px] animate-random-move-alternate"></div>
      </div>

      <section id="about" class="py-32 px-6 min-h-screen flex items-center relative overflow-hidden">

        <div class="max-w-6xl mx-auto relative z-10">
          <div class="grid md:grid-cols-2 gap-16 items-center">
            <div class="transform transition-all duration-500 hover:translate-x-2">
              <div class="inline-block px-5 py-2 bg-purple-900/40 text-purple-300 rounded-full mb-8 shadow-lg shadow-purple-900/10 border border-purple-700/30 backdrop-blur-sm">
                <span class="flex items-center">
                  <span class="w-2 h-2 bg-purple-400 rounded-full animate-pulse mr-2"></span>
                  Hello, I'm a Developer
                </span>
              </div>

              <h1 class="text-5xl md:text-7xl font-bold mb-8 leading-tight">
                <span class="text-white">Kordás</span>
                <br class="md:hidden">
                <span class="bg-gradient-to-r from-purple-400 to-fuchsia-500 bg-clip-text text-transparent">Patrik</span>
              </h1>

              <p class="text-xl text-gray-300 mb-10 leading-relaxed max-w-xl">
                Full-stack developer focused on creating intuitive and performant web solutions with Vue.js, .NET, and Node.js
              </p>

              <div class="flex flex-wrap gap-5">
                <button @click="downloadCV" class="bg-gradient-to-r from-purple-700 to-fuchsia-700 hover:from-purple-600 hover:to-fuchsia-600 px-8 py-4 rounded-xl flex items-center gap-3 transition-all duration-300 transform hover:scale-105 shadow-lg shadow-purple-900/30 group">
                  <i class="bi bi-download text-lg group-hover:animate-bounce"></i>
                  <span class="font-medium">Download CV</span>
                </button>

                <a href="#projects" class="border border-purple-700/30 bg-gray-900/50 backdrop-blur-sm hover:bg-gray-800 px-8 py-4 rounded-xl flex items-center gap-3 transition-all duration-300 transform hover:scale-105 group">
                  <span class="font-medium">View Projects</span>
                  <i class="bi bi-arrow-right text-lg group-hover:translate-x-1 transition-transform"></i>
                </a>
              </div>
            </div>

            <div class="flex justify-center">
              <div class="relative transform transition-all duration-500 hover:scale-105 hover:rotate-2">
                <div class="w-96 h-96 rounded-full overflow-hidden border-4 border-purple-500/30 shadow-2xl shadow-purple-500/30 relative z-10">
                  <img src="@/assets/profile.jpg" alt="Developer Profile" class="w-full h-full object-cover" />

                  <div class="absolute inset-0 bg-gradient-to-t from-purple-900/20 to-transparent"></div>
                </div>

                <div class="absolute -top-4 -left-4 -right-4 -bottom-4 rounded-full border border-purple-500/20 animate-pulse"></div>
                <div class="absolute -top-8 -left-8 -right-8 -bottom-8 rounded-full border border-purple-500/10 animate-pulse animation-delay-700"></div>

                <div class="absolute -bottom-4 -right-4 bg-gray-900/90 px-5 py-3 rounded-xl border border-purple-500/30 shadow-lg transform hover:scale-105 transition-transform z-20">
                  <div class="flex items-center gap-3">
                    <div class="w-3 h-3 bg-purple-400 rounded-full animate-pulse"></div>
                    <span class="text-purple-300 font-medium">Available for hire</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="absolute bottom-10 left-0 right-0 flex justify-center">
          <a href="#skills"
             class="animate-bounce rounded-full p-3  transform transition-all duration-300 hover:scale-110 bg-transparent">
            <i class="bi bi-chevron-down text-xl text-purple-300"></i>
          </a>
        </div>
      </section>



      <section id="skills" class="py-32 px-6 relative overflow-hidden">



        <div class="max-w-6xl mx-auto relative z-10">
          <SectionTitle>
            <span class="text-5xl">My Skills & Expertise</span>
          </SectionTitle>

          <div class="grid md:grid-cols-1 lg:grid-cols-3 gap-10 mt-16">
            <SkillsCard title="Frontend Development" icon="bi-code-slash"
                        class="transform transition-all duration-500 hover:scale-105 hover:-rotate-1">
              <div class="grid sm:grid-cols-2 gap-4">
                <SkillItem v-for="skill in frontendSkills" :key="skill.name"
                           :name="skill.name" :icon="skill.icon"
                           class="text-lg py-3" />
              </div>
            </SkillsCard>

            <SkillsCard title="Backend Development" icon="bi-server"
                        class="transform transition-all duration-500 hover:scale-105 hover:rotate-1">
              <div class="grid sm:grid-cols-2 gap-4">
                <SkillItem v-for="skill in backendSkills" :key="skill.name"
                           :name="skill.name" :icon="skill.icon"
                           class="text-lg py-3" />
              </div>
            </SkillsCard>

            <SkillsCard title="Tools & DevOps" icon="bi-tools"
                        class="transform transition-all duration-500 hover:scale-105 hover:-rotate-1">
              <div class="grid sm:grid-cols-2 gap-4">
                <SkillItem v-for="skill in toolsSkills" :key="skill.name"
                           :name="skill.name" :icon="skill.icon"
                           class="text-lg py-3" />
              </div>
            </SkillsCard>
          </div>

          <div class="mt-16 text-center">
            <div class="inline-block px-6 py-3 bg-purple-900/30 text-purple-300 rounded-xl border border-purple-500/20 transform transition-all duration-300 hover:scale-105">
              <span class="text-xl">Always expanding my skillset</span>
            </div>
          </div>
        </div>
      </section>


      <section id="projects" class="py-32 px-6 relative overflow-hidden">



        <div class="max-w-6xl mx-auto relative z-10">
          <SectionTitle>
            <span class="text-5xl">Featured Projects</span>
          </SectionTitle>

          <p class="text-center text-xl text-gray-400 mb-16 max-w-2xl mx-auto">
            Explore my latest work that showcases my technical skills and problem-solving approach
          </p>

          <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-10">
            <ProjectCard
                v-for="(project, index) in projects"
                :key="project.title"
                :project="{
                  ...project,
                }"
                class="transform transition-all duration-500 hover:scale-105 hover:shadow-2xl hover:shadow-purple-500/20"
                :class="{'hover:rotate-1': index % 2 === 0, 'hover:-rotate-1': index % 2 !== 0}"
            />
          </div>

          <div class="mt-20 text-center">
            <a href="https://github.com/b0korpat" target="_blank" class="inline-block px-8 py-4 bg-gradient-to-r from-purple-900/40 to-fuchsia-900/40 hover:from-purple-900/60 hover:to-fuchsia-900/60 text-purple-300 rounded-xl border border-purple-500/20 transform transition-all duration-300 hover:scale-105 backdrop-blur-sm">
              <span class="text-xl flex items-center gap-2">
                <i class="bi bi-github"></i>
                View All Projects <i class="bi bi-arrow-right"></i>
              </span>
            </a>
          </div>
        </div>
      </section>

      <footer class="py-16 px-6 border-t border-purple-900/30 relative overflow-hidden">
        <div class="absolute bottom-0 left-0 w-full h-1 bg-gradient-to-r from-purple-800/0 via-purple-800/50 to-fuchsia-800/0"></div>

        <div class="max-w-6xl mx-auto flex flex-col md:flex-row justify-between items-center gap-8 relative z-10">
          <div class="flex flex-col items-center md:items-start">
            <div class="text-2xl font-bold mb-3 flex items-center">
              <span class="text-purple-400 mr-1">K.</span>
              <span class="text-white">Patrik</span>
            </div>
            <p class="text-gray-400 mb-4 text-center md:text-left">© 2025 Kordás Patrik. All rights reserved.</p>
            <div class="flex space-x-6 mt-2">
              <SocialIcon href="https://github.com/b0korpat" icon="bi-github" />
              <SocialIcon href="www.linkedin.com/in/patrik-kordás-b8479a20a" icon="bi-linkedin" />
              <SocialIcon href="https://www.facebook.com/kordas.patrik/" icon="bi-facebook" />
            </div>
          </div>

          <div class="flex flex-col md:flex-row gap-8">
            <div>
              <h3 class="text-lg font-semibold text-purple-300 mb-3">Quick Links</h3>
              <ul class="space-y-2">
                <li><a href="#about" class="text-gray-400 hover:text-purple-300 transition-colors">About</a></li>
                <li><a href="#skills" class="text-gray-400 hover:text-purple-300 transition-colors">Skills</a></li>
                <li><a href="#projects" class="text-gray-400 hover:text-purple-300 transition-colors">Projects</a></li>
              </ul>
            </div>

            <div class="bg-gray-900/60 backdrop-blur-sm border border-purple-800/30 rounded-xl px-6 py-4 transform transition-all duration-300 hover:scale-105">
              <p class="text-purple-300 font-medium mb-2">Let's connect</p>
              <a href="mailto:kordas.patrik@gmail.com" class="flex items-center text-gray-300 hover:text-purple-300 transition-colors gap-2">
                <i class="bi bi-envelope"></i> kordas.patrik@gmail.com
              </a>
            </div>
          </div>
        </div>
      </footer>
    </main>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import NavLink from '@/components/NavLink.vue'
import SocialIcon from '@/components/SocialIcon.vue'
import SkillsCard from '@/components/SkillsCard.vue'
import SkillItem from '@/components/SkillItem.vue'
import ProjectCard from '@/components/ProjectCard.vue'
import SectionTitle from '@/components/SectionTitle.vue'

const navLinks = [
  { id: 'about', href: '#about', icon: 'bi-house', label: 'Home' },
  { id: 'skills', href: '#skills', icon: 'bi-lightbulb', label: 'Skills' },
  { id: 'projects', href: '#projects', icon: 'bi-briefcase', label: 'Projects' },]

const frontendSkills = ref([
  { name: 'Vue.js', icon: 'bi-caret-down-fill' },
  { name: 'Ionic', icon: 'bi-vinyl' },
  { name: 'HTML/CSS', icon: 'bi-filetype-html' },
  { name: 'Bootstrap', icon: 'bi-bootstrap' }
])

const backendSkills = ref([
  { name: '.NET Core', icon: 'bi-code-square' },
  { name: 'Node.js', icon: 'bi-hdd-stack' },
  { name: 'C#', icon: 'bi-braces' },
  { name: 'SQL', icon: 'bi-database' }
])

const toolsSkills = ref([
  { name: "Git", icon: "bi-git" },
  { name: "Docker", icon: "bi-box" },
  { name: "CI/CD", icon: "bi-diagram-3" },
  { name: "Railway", icon: "bi-cloud" }
])

const projects = ref([
  {
    title: 'Vasvári App',
    description: 'Full-stack application built with Vue.js and Asp.NET Core to make school life easier',
    tech: ['Vue.js','Ionic', 'Asp.NET Core', 'MySQL', 'Docker', 'Railway'],
    link: 'https://vasvariapp.hu',
    image: '/vasvariApp.png'
  },
  {
    title: 'Tick-tac-toe',
    description: 'An easy vue project to test my skills ',
    tech: ['Vue.js', 'Tailwind'],
    link: 'https://tick-tac-toe-xi.vercel.app/',
    image: '/TicTacToe.png',
    github:'https://github.com/b0korpat/TickTacToe'
  },
  {
    title: 'Random Small Projects',
    description: 'All the small project that accumulated during my studies',
    tech: ['Node.js', 'Bootstrap', 'SQLite', 'Vue.js', 'Html/CSS'],
    github: 'https://github.com/b0korpat/Webprog',
    image: '/webprog.png'
  }
])

// Sidebar state
const sidebarOpen = ref(false)

const toggleSidebar = () => {
  sidebarOpen.value = !sidebarOpen.value
}

const activeSection = ref('about')
const sections = ref([])

const handleScroll = () => {
  const currentScrollPos = window.scrollY
  const scrollHeight = window.innerHeight * 0.3

  for (let i = sections.value.length - 1; i >= 0; i--) {
    const section = sections.value[i]
    const sectionTop = section.offsetTop - scrollHeight

    if (currentScrollPos >= sectionTop) {
      activeSection.value = section.id
      break
    }
  }
}

onMounted(() => {
  sections.value = Array.from(document.querySelectorAll('section[id]'))
  window.addEventListener('scroll', handleScroll)
  handleScroll()

})


const downloadCV = () => {
  const link = document.createElement('a')
  link.href = '/CV_Kordás_Patrik.pdf'
  link.download = '/CV_Kordás_Patrik.pdf'
  link.click()
}
</script>
<style>
@keyframes random-move {
  0%, 100% {
    transform: translate(0, 0) rotate(0deg);
  }
  20% {
    transform: translate(30px, -20px) rotate(5deg);
  }
  40% {
    transform: translate(-20px, 40px) rotate(-5deg);
  }
  60% {
    transform: translate(10px, 30px) rotate(10deg);
  }
  80% {
    transform: translate(-30px, -10px) rotate(-10deg);
  }
}

@keyframes random-move-delayed {
  0%, 100% {
    transform: translate(0, 0) rotate(0deg);
  }
  25% {
    transform: translate(-40px, 20px) rotate(-5deg);
  }
  50% {
    transform: translate(30px, 30px) rotate(8deg);
  }
  75% {
    transform: translate(10px, -40px) rotate(-8deg);
  }
}

@keyframes random-move-alternate {
  0%, 100% {
    transform: translate(0, 0) rotate(0deg);
  }
  15% {
    transform: translate(-25px, -15px) rotate(-10deg);
  }
  35% {
    transform: translate(35px, 10px) rotate(5deg);
  }
  55% {
    transform: translate(-15px, 25px) rotate(-5deg);
  }
  75% {
    transform: translate(25px, -25px) rotate(10deg);
  }
}

.animate-random-move {
  animation: random-move 25s ease-in-out infinite;
}

.animate-random-move-delayed {
  animation: random-move-delayed 30s ease-in-out infinite;
}

.animate-random-move-alternate {
  animation: random-move-alternate 28s ease-in-out infinite;
}
</style>