<!-- src/components/Aside.vue -->
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
                    <svg width="21" height="21" viewBox="0 0 21 21" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M17.2615 16.913H3.81592C2.8877 16.913 2.13522 16.1606 2.13522 15.2323V5.07505C2.17439 4.1755 2.91551 3.46661 3.81592 3.46747H17.2615C18.1897 3.46747 18.9422 4.21994 18.9422 5.14816V15.2323C18.9422 16.1606 18.1897 16.913 17.2615 16.913ZM3.81592 6.71793V15.2323H17.2615V6.71793L10.5387 11.1987L3.81592 6.71793ZM4.4882 5.14816L10.5387 9.18183L16.5892 5.14816H4.4882Z" fill="currentColor"/>
                    </svg>
                </div>
                <div class="block__info">
                    <div class="block__name">Email</div>
                    <a :href="`mailto:${contacts.mail}`" class="block__text">{{ contacts.mail }}</a>
                </div>
            </li>
            <li class="block__item">
                <div class="block__icon">
                    <svg width="21" height="21" viewBox="0 0 21 21" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M7.56808 17.2498C5.86876 17.2498 4.33675 16.2262 3.68634 14.6563C3.03593 13.0863 3.39519 11.2792 4.59661 10.0774L6.37983 8.2942L7.56808 9.48245L5.7857 11.2648C5.14877 11.9018 4.90002 12.8301 5.13315 13.7002C5.36628 14.5702 6.04588 15.2498 6.91595 15.483C7.78602 15.7161 8.71436 15.4674 9.3513 14.8304L11.1337 13.0481L12.3219 14.2371L10.5395 16.0195C9.75304 16.8099 8.6831 17.2529 7.56808 17.2498ZM8.1622 13.6422L6.97395 12.4539L12.9161 6.51182L14.1043 7.70008L8.16304 13.6413L8.1622 13.6422ZM14.6993 11.8598L13.5102 10.6715L15.2926 8.88917C15.9382 8.25414 16.1936 7.32164 15.9617 6.44626C15.7298 5.57088 15.0462 4.88714 14.1709 4.65503C13.2955 4.42292 12.363 4.67812 11.7278 5.32357L9.94458 7.10595L8.75633 5.9177L10.5395 4.13448C12.1825 2.50586 14.8329 2.51166 16.4687 4.14746C18.1045 5.78327 18.1103 8.43363 16.4817 10.0766L14.6993 11.859V11.8598Z" fill="currentColor"/>
                    </svg>
                </div>
                <div class="block__info">
                    <div class="block__name">Website</div>
                    <a :href="contacts.site" class="block__text">{{ contacts.site }}</a>
                </div>
            </li>
            <li class="block__item">
                <div class="block__icon">
                    <svg width="21" height="22" viewBox="0 0 21 22" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M16.4191 17.6874C9.24953 17.6976 3.80829 12.1911 3.81596 5.08431C3.81596 4.6202 4.19219 4.24185 4.6563 4.24185H6.87428C7.29074 4.24185 7.64452 4.54785 7.70567 4.95979C7.85223 5.94708 8.13968 6.90825 8.55928 7.81392L8.64563 8.00031C8.76571 8.25948 8.68432 8.56741 8.45188 8.7334C7.76499 9.22393 7.50249 10.2113 8.0376 10.9817C8.70911 11.9485 9.55557 12.7948 10.5222 13.466C11.2925 14.001 12.2798 13.7385 12.7703 13.0518C12.9364 12.8192 13.2445 12.7378 13.5038 12.8579L13.6893 12.9438C14.5951 13.3634 15.5563 13.6509 16.5437 13.7974C16.9557 13.8585 17.2615 14.2123 17.2615 14.6288V16.8471C17.2615 17.3112 16.8844 17.6874 16.4202 17.6874L16.4191 17.6874Z" fill="currentColor"/>
                    </svg>
                </div>
                <div class="block__info">
                    <div class="block__name">Phone</div>
                    <a :href="`tel:${contacts.phone.replace(/\D/g, '')}`
                    " class="block__text">{{ contacts.phone }}</a>
                </div>
            </li>
            <li class="block__item">
                <div class="block__icon">
                    <svg width="21" height="21" viewBox="0 0 21 21" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M10.5387 17.7634C9.4773 16.8581 8.49347 15.8655 7.5975 14.7962C6.25294 13.1903 4.65628 10.7986 4.65628 8.51962C4.65509 6.13937 6.08844 3.99299 8.28748 3.08206C10.4865 2.17113 13.0178 2.6752 14.7001 4.35906C15.8064 5.46042 16.4261 6.95858 16.4212 8.51962C16.4212 10.7986 14.8245 13.1903 13.4799 14.7962C12.584 15.8655 11.6001 16.8581 10.5387 17.7634ZM10.5387 5.99858C9.63804 5.99858 8.80577 6.47908 8.35543 7.2591C7.90509 8.03911 7.90509 9.00013 8.35543 9.78014C8.80577 10.5602 9.63804 11.0407 10.5387 11.0407C11.9311 11.0407 13.0598 9.91195 13.0598 8.51962C13.0598 7.12728 11.9311 5.99858 10.5387 5.99858Z" fill="#79819A"/>
                    </svg>
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

    a.block__text:hover {
        color:  #5D5FEF;
    }
</style>
