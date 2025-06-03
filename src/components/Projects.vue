<!-- src/components/Projects.vue -->
<template>
    <section class="section projects">
        <h2 class="section__title">Latest projects</h2>
        <div class="projects__wrap">
            <div class="project-card"
            v-for="(project, index) in projects"
            :key="index"
            >
                <div class="project-card__img">
                    <img :src="project.img" />
                </div>
                <div class="project-card__title">{{ project.title }}</div>
                <div class="project-card__text">{{ project.text }}</div>
                <a :href="project.link" class="project-card__link">
                    <span class="project-card__link-icon">
                        <img :src="project.iconLink" />
                    </span>
                    <span>{{ project.link }}</span>
                </a>
            </div>
        </div>
    </section>
</template>

<script setup>
    const projects = [
        {
            img: new URL('@/assets/img/logo9.svg', import.meta.url).href,
            title: 'Portfolio Webpage',
            text: 'Personal Portfolio webpage',
            link: 'https://jein-sh.github.io/',
            iconLink: new URL('@/assets/img/icon-link.svg', import.meta.url).href
        },
        {
            img: new URL('@/assets/img/img10.png', import.meta.url).href,
            title: 'Scrum360',
            text: 'New version of company website',
            link: 'https://scrum360.ru/',
            iconLink: new URL('@/assets/img/icon-link.svg', import.meta.url).href
        },
    ]
</script>

<style scored>
    .projects__wrap {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        border-radius: 8px;
        overflow: hidden;
        gap: 8px;
    }


    @media(max-width: 1024px) {
        .projects__wrap {
            grid-template-columns: 1fr;
        }
    }

    .project-card {
        display: grid;
        grid-template-columns: 64px 1fr;
        padding: 24px;
        width: 100%;
        background: #F7F9FC;
    }

    .project-card__img {
        width: 48px;
        height: 48px;
        margin-right: 16px;
        grid-row: 1 / 3;
        margin-bottom: 16px;
    }

    .project-card__img img {
        width: 100%;
        height: 100%;
        object-fit: contain;
        border-radius: 8px;
    }

    .project-card__title {
        font-weight: 500;
        font-size: 16px;
        line-height: 20px;
        color: #2E2E48;
        margin-bottom: 4px;
    }

    .project-card__text {
        font-size: 14px;
        line-height: 18px;
        letter-spacing: 0.01em;
        color: #79819A;
    }

    .project-card__link {
        display:flex;
        align-items: center;
        gap: 12px;
        grid-column: 1 / -1;
        font-family: 'Outfit';
        font-weight: 600;
        font-size: 16px;
        line-height: 125%;
        text-decoration-line: underline;
        color: #516CF7;
        transition: color 0.3s ease;
        word-break: break-all;
    }

    .project-card__link:hover {
        color: #2E2E48;
    }

    .project-card__link-icon {
        flex-shrink: 0;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 24px;
        height: 24px;
        border-radius: 50%;
        background: #E1E7FE;
        transition: background 0.3s ease;
    }

    .project-card__link-icon img {
        width: 15px;
        height: 15px;
    }

    .project-card__link:hover .project-card__link-icon {
        background: #E2E6EE
    }
</style>
