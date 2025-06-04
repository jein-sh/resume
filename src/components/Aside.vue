<template>
    <div class="header">
        <div class="header__img">
            <img :src="user.avatar" alt="avatar">
        </div>
        <h1 class="header__name">{{ user.name }}</h1>
    </div>

    <div class="about">
        <p>{{ user.aboutText }}</p>
    </div>

    <div class="divider"></div>

    <div class="block contatcs">
        <ul class="block__list">
            <li class="block__item">
                <div class="block__icon">
                    <inline-svg :src="mailIcon" />
                </div>
                <div class="block__info">
                    <div class="block__name">Email</div>
                    <a :href="`mailto:${contacts.mail}`" class="block__text">{{ contacts.mail }}</a>
                </div>
            </li>
            <li class="block__item">
                <div class="block__icon">
                    <inline-svg :src="linkIcon" />
                </div>
                <div class="block__info">
                    <div class="block__name">Website</div>
                    <a :href="contacts.site" class="block__text">{{ contacts.site }}</a>
                </div>
            </li>
            <li class="block__item">
                <div class="block__icon">
                    <inline-svg :src="phoneIcon" />
                </div>
                <div class="block__info">
                    <div class="block__name">Phone</div>
                    <a :href="`tel:${contacts.phone.replace(/\D/g, '')}`
                    " class="block__text">{{ contacts.phone }}</a>
                </div>
            </li>
            <li class="block__item">
                <div class="block__icon">
                    <inline-svg :src="pinIcon" />
                </div>
                <div class="block__info">
                    <div class="block__name">Address</div>
                    <p class="block__text">{{ contacts.address }}</p>
                </div>
            </li>
        </ul>
    </div>

    <div class="divider"></div>

    <div class="block socials">
        <div class="block__title">Socials</div>
        <ul class="block__list">
            <li v-for="(social, index) in socials" :key="index" class="block__item">
                <div class="block__img">
                    <img :src="social.icon" :alt="social.name">
                </div>
                <div class="block__info">
                    <div class="block__name">{{ social.name }}</div>
                    <a :href="social.link" class="block__text">{{ social.handle }}</a>
                </div>
            </li>
        </ul>
    </div>
    <div class="divider"></div>

    <div class="block languages">
        <div class="block__title">Languages</div>
        <ul class="block__list">
            <li v-for="(lang, index) in languages" :key="index" class="block__item">
                <div class="block__img">
                    <img :src="lang.flag" :alt="lang.name">
                </div>
                <div class="block__info">
                    <div class="block__text">{{ lang.name }}</div>
                    <p class="block__name">{{ lang.level }}</p>
                </div>
            </li>
        </ul>
    </div>

    <div class="block hobbies">
        <div class="block__title">Hobbies & Interests</div>
        <ul class="block__list">
            <li v-for="(hobby, index) in hobbies" :key="index" class="block__item">
                <div class="block__img">
                    <img :src="hobby.icon" :alt="hobby.name">
                </div>
                <div class="block__info">
                    <div class="block__text">{{ hobby.name }}</div>
                </div>
            </li>
        </ul>
    </div>
</template>

<script setup>
    import InlineSvg from 'vue-inline-svg'
    
    const mailIcon = new URL('@/assets/img/svg/mail.svg', import.meta.url).href
    const linkIcon = new URL('@/assets/img/svg/link.svg', import.meta.url).href
    const phoneIcon = new URL('@/assets/img/svg/phone.svg', import.meta.url).href
    const pinIcon = new URL('@/assets/img/svg/pin.svg', import.meta.url).href

    const user = {
        name: 'Евгения Шамарина',
        avatar: new URL('@/assets/img/avatar.png', import.meta.url).href,
        aboutText: 'Я frontend-разработчик с опытом работы три года. Работала бухгалтером, в 2021 году решила сменить сферу деятельности. Меня привлекает разработка веб-сайтов и приложений, улучшающих жизнь людей и помогающих решать их проблемы. Стремлюсь стать частью дружной и профессиональной команды, в которой я могла бы расти как frontend-разработчик и развивать свои навыки для достижения командных результатов.'
    }

    const contacts = {
        mail: 'jein.sh85@gmail.com',
        site: 'https://jein-sh.github.io/',
        phone: ' +7 (921) 610-12-53',
        address: 'Россия, Калининград'
    }

    const socials = [
        { name: 'Telegram', handle: '@jeinshamarina', icon: new URL('@/assets/img/icon5.svg', import.meta.url).href, link: 'https://t.me/jeinshamarina' },
        { name: 'Github', handle: '@jein-sh', icon: new URL('@/assets/img/icon2.svg', import.meta.url).href, link: 'https://github.com/jein-sh' },
    ]

    const languages = [
        { name: 'English', level: 'A2 – Elementary (Basic User)', flag: new URL('@/assets/img/flag2.svg', import.meta.url).href },
    ]

    const hobbies = [
        { name: 'Cycling', icon: new URL('@/assets/img/img11.svg', import.meta.url).href },
        { name: 'Reading books', icon: new URL('@/assets/img/img12.svg', import.meta.url).href },
        { name: 'Embroidery', icon: new URL('@/assets/img/img13.svg', import.meta.url).href },
        { name: 'Backpacking', icon: new URL('@/assets/img/img14.svg', import.meta.url).href },
    ]
</script>

<style scoped>
    .header__img {
        width: 97px;
        height: 97px;
        border-radius: 50%;
        overflow: hidden;
        margin-bottom: 16px;
    }

    .header__img img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .header__name {
        font-family: 'Outfit', 'Arial', sans-serif;
        font-weight: 500;
        font-size: 32px;
        line-height: 40px;
        letter-spacing: -0.02em;
        color: #2E2E48;
    }

    .about {
        font-family: 'Outfit', 'Arial', sans-serif;
        font-weight: 500;
        font-size: 18px;
        line-height: 24px;
        letter-spacing: 0.02em;
        color: #47516B;
    }

    .about p {
        margin: 0 0 10px;
    }

    .divider {
        height: 1px;
        width: 100%;
        background-color: #E2E6EE;
    }

    .block__title {
        font-size: 12px;
        line-height: 16px;
        letter-spacing: 0.01em;
        color: #79819A;
        margin-bottom: 20px;
    }

    .block__list {
        list-style: none;
        padding: 0;
        margin: 0;
        display: grid;
        gap: 24px;
    }

    .block__item {
        display: flex;
        align-items: center;
        gap: 16px;
    }

    .block__icon {
        flex-shrink: 0;
        width: 32px;
        height: 32px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 50%;
        overflow: hidden;
        background-color: #E2E6EE;
        transition: color 0.3s ease;
    }

    .block__icon svg {
        width: 20px;
        height: 20px;
    }

    .block__img {
        flex-shrink: 0;
        width: 32px;
        height: 32px;
    }

    .block__img img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .block__name {
        letter-spacing: 0.01em;
        color: #79819A;
        margin-bottom: 4px;
    }

    .block__text {
        font-weight: 500;
        font-size: 14px;
        line-height: 18px;
        color: #47516B;
        transition: color 0.3s ease;
    }

    a.block__text{
        word-break: break-all;
    }

    a.block__text:hover,
    .block__item:has(a:hover) .block__icon {
        color:  #5D5FEF;
    }
</style>
