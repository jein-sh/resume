<template>
    <section class="section achievements">
        <h2 class="section__title">Achievements</h2>
        <div class="achievements__wrap">
            <div
                v-for="(item, index) in achievements"
                :key="index"
                class="achievement-card"
            >
                <div class="achievement-card__time">
                    <span class="achievement-card__date">{{ item.date }}</span>
                    <span v-if="item.present" class="tag">Present</span>
                    <span class="achievement-card__place">{{ item.place }}</span>
                </div>
                <div class="achievement-card__img">
                    <img :src="item.img" alt="" />
                </div>
                <div class="achievement-card__position">{{ item.position }}</div>
                <div class="achievement-card__company">{{ item.company }}</div>
                <div class="achievement-card__desc">{{ item.desc }}</div>
            </div>
        </div>
    </section>
</template>

<script setup>
    const achievements = [
        {
            present: true,
            date: 'Апрель 2024 - ',
            place: 'Online',
            img: new URL('@/assets/img/img10.png', import.meta.url).href,
            position: 'Frontend-разработчик',
            company: 'Scrum360',
            desc: 'Верстка сайтов по макетам Figma, Разработка сайтов на Modx и Wordpress, техническая поддержка сайтов на Modx, WP, Bitrix, Opencart'
        },
        {
            date: 'Ноябрь 2022 - Декабрь 2022',
            place: 'Калининград',
            img: new URL('@/assets/img/img9.png', import.meta.url).href,
            position: 'Стажер Frontend-разработчик',
            company: 'KODE',
            desc: 'Стажировка: Pазработка банковского приложения на React Native. Страницы платежей, оплаты, авторизации'
        },
        {
            date: 'Июнь 2022 - Декабрь 2023',
            place: 'Online',
            img: new URL('@/assets/img/logo16.svg', import.meta.url).href,
            position: 'Верстальщик',
            company: 'ЛигаА',
            desc: 'Верстка сайтов с использованием HTML, PUG, CSS, SCSS, JavaScript. Поиск и устранение багов. Взаимодействие с командой: менеджером проекта, тестировщиками, разработчиками, дизайнерами и др.'
        },
    ]
</script>

<style scored>
    .achievements__wrap {
        display: grid;
    }

    .achievement-card {
        position: relative;
        display: grid;
        grid-template-columns: 56px 185px 1fr;
        grid-template-areas: "time time desc"
            "img position desc"
            "img company desc";
        padding: 6px 0 20px 40px;
    }

    .achievement-card::before {
        content: "";
        position: absolute;
        left: 8px;
        top: 9px;
        width: 6px;
        height: 6px;
        border-radius: 50%;
        background-color: #2E2E48;
    }

    .achievement-card::after {
        content: "";
        position: absolute;
        left: 10px;
        bottom: 0;
        width: 1px;
        height: calc(100% - 24px);
        background-color: #F7F9FC;
    }

    .achievement-card__time {
        grid-area: time;
        display: flex;
        align-items: center;
        gap: 4px;
        font-size: 10px;
        line-height: 13px;
        letter-spacing: 0.01em;
        color: #47516B;
        margin-bottom: 8px;
    }

    .achievement-card__place {
        display: inline-flex;
        align-items: center;
        gap: 4px;
        color: #79819A;
    }

    .achievement-card__place::before {
        content: "";
        width: 12px;
        height: 12px;
        background-image: url(@/assets/img/marker.svg);
        background-position: center;
        background-size: cover;
    }

    .achievement-card__img {
        grid-area: img;
        width: 40px;
        height: 40px;
        margin-right: 16px;
    }

    .achievement-card__img img {
        width: 100%;
        height: 100%;
        object-fit: contain;
    }

    .achievement-card__position {
        grid-area: position;
        font-size: 12px;
        line-height: 16px;
        letter-spacing: 0.01em;
        color: #79819A;
        margin-bottom: 4px;
    }

    .achievement-card__company {
        grid-area: company;
        font-weight: 500;
        font-size: 14px;
        line-height: 18px;
        color: #2E2E48;
    }

    .achievement-card__desc {
        grid-area: desc;
        font-size: 12px;
        line-height: 16px;
        letter-spacing: 0.01em;
        color: #79819A;
    }

    @media(max-width: 1024px) {
        .achievement-card {
            grid-template-columns: 56px 1fr;
            grid-template-areas: "time time"
            "img position"
            "img company"
            "desc desc";
        }

        .achievement-card__company {
            margin-bottom: 16px;
        }
    }
</style>