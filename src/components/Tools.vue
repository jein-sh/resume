<template>
    <section class="section tools">
        <h2 class="section__title">Tools/Skills</h2>
        <div class="tools__wrap">
            <div
                class="tool-card"
                v-for="(tool, index) in tools"
                :key="index"
                >
                <div class="tool-card__img">
                    <img :src="tool.icon" alt="logo" />
                </div>
                <div class="tool-card__title">{{ tool.title }}</div>
                <div class="tool-card__text">{{ tool.text }}</div>
            </div>
        </div>
    </section>
</template>

<script setup>
    const tools = [
        {
            icon: new URL('@/assets/img/logo4.svg', import.meta.url).href,
            title: 'HTML 5',
            text: 'Structural Design'
        },
        {
            icon: new URL('@/assets/img/logo5.svg', import.meta.url).href,
            title: 'CSS 3',
            text: 'Style Design'
        },
        {
            icon: new URL('@/assets/img/logo18.svg', import.meta.url).href,
            title: 'JS',
            text: 'Behavioral Development'
        },
        {
            icon: new URL('@/assets/img/logo.svg', import.meta.url).href,
            title: 'Figma',
            text: 'Design Interpretation & Implementation'
        },
        {
            icon: new URL('@/assets/img/logo6.svg', import.meta.url).href,
            title: 'Wordpress',
            text: 'Web development'
        },
        {
            icon: new URL('@/assets/img/logo17.svg', import.meta.url).href,
            title: 'Modx',
            text: 'Web development'
        },
        {
            icon: new URL('@/assets/img/logo7.svg', import.meta.url).href,
            title: 'VS Code',
            text: 'Code editor'
        },
        {
            icon: new URL('@/assets/img/logo19.svg', import.meta.url).href,
            title: 'Git',
            text: 'Collaboration Development'
        }
    ]
</script>

<style scored>
    .tools__wrap {
        display: grid;
        grid-template-columns: repeat(15, 1fr);
        border-radius: 8px;
        overflow: hidden;
        gap: 8px;
    }

    @media(max-width: 1239px) {
        .tools__wrap {
            grid-template-columns: repeat(6, 1fr);
        }
    }

    @media(max-width: 546px) {
        .tools__wrap {
            grid-template-columns: repeat(2, 1fr);
        }
    }

    .tool-card {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 16px;
        gap: 8px;
        width: 100%;
        background: #F7F9FC;
        grid-column: auto / span 3;
    }

    .tool-card:nth-child(8n+1),
    .tool-card:nth-child(8n+2),
    .tool-card:nth-child(8n+3) {
        grid-column: auto / span 5;
    }

    .tool-card__img {
        width: 48px;
        height: 48px;
    }

    .tool-card__img img {
        width: 100%;
        height: 100%;
        object-fit: contain;
    }

    .tool-card__title {
        font-weight: 500;
        font-size: 14px;
        line-height: 130%;
        color: #2E2E48;
    }

    .tool-card__text {
        font-size: 10px;
        line-height: 13px;
        text-align: center;
        letter-spacing: 0.01em;
        color: #79819A;
    }


    @media(max-width: 1239px) {
        .tool-card,
        .tool-card:nth-child(8n+1),
        .tool-card:nth-child(8n+2),
        .tool-card:nth-child(8n+3) {
            grid-column: auto / span 2;
        }

        .tool-card:nth-child(8n+4),
        .tool-card:nth-child(8n+5) {
            grid-column: auto / span 3;
        }
    }

    @media(max-width: 546px) {
        .tool-card,
        .tool-card:nth-child(8n+1),
        .tool-card:nth-child(8n+2),
        .tool-card:nth-child(8n+3),
        .tool-card:nth-child(8n+4),
        .tool-card:nth-child(8n+5) {
            grid-column: auto / span 1;
        }
    }
</style>