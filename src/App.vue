<!-- src/App.vue -->
<template>
    <main>
        <div class="wrapper">
            <div class="left">

                <Aside />

            </div>

            <div class="right">

                <Education />

                <Achievements />

                <Tools />

                <Projects />

                <Awards />

            </div>
        </div>
    </main>
</template>
  
<script setup>
    import Aside from './components/Aside.vue';
    import Education from './components/Education.vue';
    import Achievements from './components/Achievements.vue';
    import Tools from './components/Tools.vue';
    import Projects from './components/Projects.vue';
    import Awards from './components/Awards.vue';
</script>