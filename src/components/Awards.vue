<template>
    <section class="section awards">
        <h2 class="section__title">Certificates & Awards</h2>
        <div class="awards__wrap">
            <div class="award-card"
                v-for="(item, index) in awards"
                :key="index">
                <div class="award-card__img">
                    <img :src="item.icon" alt="{{ item.title }}">
                </div>
                <div class="award-card__text">{{ item.text }}</div>
                <div class="award-card__title">{{ item.title }}</div>
                <div class="award-card__date">{{ item.date }}</div>
            </div>
        </div>
    </section>
</template>

<script setup>
    const awards = [
        {
            icon: new URL('@/assets/img/logo15.svg', import.meta.url).href,
            title: 'Профессия «Фронтенд-разработчик»',
            text: 'HTMLacademy',
            date: 'Май 2021 - Апрель 2022',
        },
        {
            icon: new URL('@/assets/img/logo15.svg', import.meta.url).href,
            title: 'JavaScript. Архитектура клиентских приложений',
            text: 'HTMLacademy',
            date: 'Апрель 2022 - Июнь 2022',
        },
        {
            icon: new URL('@/assets/img/logo15.svg', import.meta.url).href,
            title: 'React. Разработка сложных клиентских приложений',
            text: 'HTMLacademy',
            date: 'Июль 2022 - Сентябрь 2022',
        },
    ]
</script>

<style scored>
    .awards__wrap {
        display: grid;
        border-radius: 8px;
        overflow: hidden;
        gap: 8px;
    }

    .award-card {
        display: grid;
        grid-template-columns: 43px 1fr max-content;
        padding: 16px 23px;
        gap: 0 12px;
        background: #F7F9FC;
    }

    .award-card__img {
        grid-row: 1 / 3;
        width: 43px;
        height: 43px;
    }

    .award-card__img img {
        width: 100%;
        height: 100%;
        object-fit: contain;
    }

    .award-card__text {
        font-size: 14px;
        line-height: 17px;
        letter-spacing: 0.01em;
        color: #79819A;
        margin-bottom: 4px;
    }

    .award-card__title {
        font-weight: 500;
        font-size: 16px;
        line-height: 19px;
        color: #2E2E48;
    }

    .award-card__date {
        grid-row: 1 / 3;
        grid-column: -2 / -1;
        font-size: 12px;
        line-height: 16px;
        letter-spacing: 0.01em;
        color: #47516B;
    }

    @media(max-width: 546px) {
        .award-card {
            grid-template-columns: 43px 1fr;
            padding: 16px;
        }

        .award-card__date {
            margin-top: 24px;;
            grid-row: auto;
            grid-column: 1 / -1;
        }
    }
</style>