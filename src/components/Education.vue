<template>
    <section class="section education">
        <h2 class="section__title">Education</h2>
        <div class="education__wrap">
            <div class="education-card"                 
                v-for="(item, index) in educationItems"
                :key="index">
                <div class="education-card__top">
                    <div class="education-card__icon">
                        <img :src="item.icon" alt="{{ item.title }}"/>
                    </div>
                    <div class="education-card__name">{{ item.title }}</div>
                </div>
                <div class="education-card__title">{{ item.course }}</div>
                <div class="education-card__date">{{ item.date }}</div>
                <div v-if="item.present" class="education-card__percent"><span class="color-iris">Percentage</span> - {{ item.percent }}</div>
            </div>
        </div>
    </section>
</template>

<script setup>
    const educationItems = [
        {
            icon: new URL('@/assets/img/img8.svg', import.meta.url).href,
            title: 'Калининградский государственный технический университет',
            course: 'Технология рыбы и рыбных продуктов, инженер-специалист',
            date: '2002 - 2007',
        },
        {
            icon: new URL('@/assets/img/logo15.svg', import.meta.url).href,
            title: 'HTMLacademy',
            course: 'Профессия «Фронтенд-разработчик»',
            date: '2021-2022',
        },
    ]
</script>

<style scored>
    .education__wrap {
        display: grid;
        gap: 8px;
        grid-template-columns: repeat(3, 1fr);
        border-radius: 8px;
        overflow: hidden;
    }

    @media(max-width: 1239px) {
        .education__wrap {
            grid-template-columns: repeat(2, 1fr);
        }
    }

    @media(max-width: 1024px) {
        .education__wrap {
            grid-template-columns: 1fr;
        }
    }

    .education-card {
        display: flex;
        flex-direction: column;
        width: 100%;
        padding: 16px 24px;
        background: #F7F9FC;
    }

    .education-card__top {
        display: flex;
        align-items: center;
        gap: 16px;
        margin-bottom: 8px;
    }

    .education-card__icon {
        width: 48px;
        height:48px;
        flex-shrink: 0;
    }

    .education-card__icon img {
        width:100%;
        height: 100%;
        object-fit: contain;
    }

    .education-card__name {
        font-weight: 500;
        font-size: 12px;
        line-height: 133%;
        color: #2E2E48;
    }

    .education-card__title {
        font-weight: 500;
        font-size: 14px;
        line-height: 18px;
        color: #2E2E48;
        margin-bottom: 2px;
        flex: 1;
    }

    .education-card__date {
        font-weight: 400;
        font-size: 10px;
        line-height: 13px;
        letter-spacing: 0.01em;
        color: #79819A;
        margin-bottom: 2px;
    }

    .education-card__percent {
        font-weight: 400;
        font-size: 12px;
        line-height: 16px;
    }
</style>