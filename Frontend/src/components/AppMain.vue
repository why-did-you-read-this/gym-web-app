<template>
    <main class="main-site">
        <section class="gym-membership">
            <img class="strong-man" src="../assets/images/gym-man.jpg" alt="Strong man in gym" width="1600"
                height="900">

            <div class="transparent-surface-over-img"></div>
            <div class="content">
                <h1 class="main-title">Стань лучшей версией себя</h1>
                <div class="buttons-wrapper">
                    <button class="button btn-try-free">Попробовать бесплатно</button>
                    <button class="button btn-buy">Купить абонемент</button>
                </div>
            </div>
        </section>

        <section class="gym-description">
            <div class="card-call-to-action">
                <img class="active-lifestyle" src="../assets/images/sneaker-lacing.jpg" alt="Girl lacing sneakers">
                <div class="description-wrapper">
                    <h2 class="title">Твой идеальный старт – здесь и сейчас!</h2>
                    <p class="subtitle">
                        Больше не нужно ждать «понедельника» или «подходящего момента». У нас ты начнешь сразу – с
                        первого визита получишь заряд энергии и четкий план действий.
                    </p>
                </div>
            </div>
            <div class="card-exercise-machines">
                <div class="description-wrapper">
                    <h2 class="title">Самые современные тренажеры – для твоих рекордов</h2>
                    <p class="subtitle">
                        Наше оборудование – топового уровня: безопасное, удобное и эффективное. Ты почувствуешь
                        разницу с первой тренировки!
                    </p>
                </div>
                <img class="pumping-up-legs" src="../assets/images/pump-up-legs.jpg" alt="Girl pumping up legs">
            </div>
        </section>

        <section class="trainers">
            <div class="trainers-description">
                <h2 class="title">Профессиональные тренеры – помогут добиться результата</h2>
                <p class="subtitle">
                    Не просто «качают», а ставят технику, подбирают программу и мотивируют.
                    С ними ты избежишь ошибок и ускоришь прогресс.
                </p>
            </div>
            <div class="cards-trainers">
                <swiper :modules="[Navigation]" :slides-per-view="3" :space-between="80" navigation
                    class="swiper-container-fix">
                    <swiper-slide class="card-trainer" v-for="(trainer, index) in trainers" :key="index">

                        <img class="trainer" :src="trainer.image" alt="">
                        <div class="text-wrapper">
                            <h4 class="trainer-name">{{ trainer.name }}</h4>
                            <p class="trainer-description">{{ trainer.description }}</p>
                        </div>
                    </swiper-slide>
                </swiper>
            </div>
        </section>

        <div class="services">
            <h2 class="title services-title">Наши услуги</h2>
            <div class="grid-container">
                <CardService title="Тренажерный зал" path="./src/assets/images/gym.jpg">
                    <Button />
                </CardService>
                <CardService title="Бассейн" path="./src/assets/images/pool.jpg">
                    <Button />
                </CardService>
                <CardService title="Групповые программы" path="./src/assets/images/group-programs.jpg">
                    <Button />
                </CardService>
                <CardService title="Персональный тренинг" path="./src/assets/images/personal-training.jpg">
                    <Button />
                </CardService>
            </div>
        </div>

        <div class="form-container">
            <h3 class="title-request">Оставьте заявку</h3>
            <p class="description-request">Пожалуйста заполните соответствующие поля данными и мы в ближайшее время вам
                позвоним</p>
            <form class="form">
                <div class="input-wrapper">
                    <input id="name" class="input-name" type="text" placeholder=" " required>
                    <label for="name">Ваше имя</label>
                </div>
                <div class="input-wrapper">
                    <input id="phone" class="input-phone" type="tel" placeholder="" required>
                    <label for="phone">Ваш телефон</label>
                </div>
                <input id="personalData" class="input-checkbox" type="checkbox" required>
                <label for="personalData" class="label-checkbox">Согласие на обработку персональных данных</label>
                <button class="button-send" type="submit">Отправить</button>
            </form>
        </div>
    </main>
</template>

<script setup>
    import { ref } from 'vue';
    import { Swiper, SwiperSlide } from 'swiper/vue';
    import { Navigation } from 'swiper/modules';
    import Button from '@components/Button.vue'
    import CardService from '@components/CardService.vue'
    import 'swiper/css/navigation';
    import 'swiper/css';

    const trainers = ref([
        { 
            name: 'Дмитрий Кожанов', 
            image: './src/assets/images/Trainer_1.png',
            description: `Специалист по силовой подготовке и пауэрлифтингу. 
                          Кандидат в мастера спорта по пауэрлифтингу. Под его 
                          руководством 15 его подопечных выполнили норматив КМС и МС.`
        },
        { 
            name: 'Виктория Серебрянская', 
            image: './src/assets/images/Trainer_2.png',
            description: `Эксперт в области пилатеса и body & mind. Владелица студии 
                          премиум-класса. Прошла обучение у лучших мировых инструкторов 
                          в США и Германии.`
        },
        { 
            name: 'Артем Волков', 
            image: './src/assets/images/Trainer_3.png',
            description: `Сертифицированный специалист по функциональному тренингу и 
                          коррекции осанки. Масер-тренер международного класса  более 
                          чем 10-летним стажем.`
        },
        { 
            name: 'Алиса Захарова', 
            image: './src/assets/images/Trainer_4.png',
            description: `Дипломированный нутрициолог и тренер по здоровому образу жизни. 
                          Специализируется на составлении программ для снижения веса без 
                          вреда для здоровья. Ведущий консультант популярного ЗОЖ-подкаста.`
        },
        { 
            name: 'Игорь Стрельников', 
            image: './src/assets/images/Trainer_5.png',
            description: `Специалист по спортивной биохакингу и подготовке к экстремальным 
                          видам спорта. Прошел стажировку в лаборатории подготовки олимпийских 
                          резервистов. Использует в работе данные фитнес-трекеров и биомаркеров 
                          для создания максимально персонализированных программ.`
        }
    ])

</script>

<style lang="scss" scoped>
    .main-site {
        width: 80%;
        margin: 0 auto;
    }

    .gym-membership {
        position: relative;
        width: 100%;
    }

    .strong-man {
        width: 100%;
        height: 85vh;
        border-radius: 1.5rem;
        object-fit: cover;
    }

    .transparent-surface-over-img {
        position: absolute;
        inset: 22% 0 0;
        border-radius: 0 0 1.5rem 1.5rem;
        background: linear-gradient(0deg, black 65%, rgba(66, 63, 63, 0.2));
        box-shadow: 0 -25px 8px rgba(66, 63, 63, 0.2);
        opacity: 0.8;
    }

    .content {
        position: absolute;
        inset: 0;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .main-title {
        font-size: 3rem;
        font-weight: bold;
        text-transform: uppercase;
        color: $light;
    }

    .buttons-wrapper {
        display: flex;
        gap: 2rem;
        margin-top: 1rem;
    }
    
    .gym-description {
        margin-top: 5rem;
        padding: 2rem;
    }

    .card-call-to-action,
    .card-exercise-machines {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .card-call-to-action {
        margin-bottom: 5rem;
    }

    .active-lifestyle,
    .pumping-up-legs {
        border-radius: 1.5rem;
    }

    .description-wrapper {
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
        width: 43.84%;
    }

    .title {
        font-size: 2rem;
        font-weight: 500;
        color: $light;
    }

    .subtitle {
        font-size: 1.2rem;
        color: $gray;
    }

    .trainers {
        margin-top: 5rem;
    }

    .trainers-description {
        width: fit-content;
        margin: 0 auto;
        margin-bottom: 5rem;
        text-align: center;

        .subtitle {
            width: 80%;
            margin: 0 auto;
            margin-top: 0.5rem;
            text-align: center;
        }
    }

    .cards-trainers {
        --swiper-navigation-color: #7f22fe;
        
        width: 100%;
    }

    .swiper-container-fix {
        z-index: 0;
        padding-inline: 3rem;
    }

    .trainer {
        width: 100%;
        height: 60%;
        object-fit: cover;
        border-radius: 1.5rem;
    }

    .text-wrapper {
        padding-inline: 1rem;
        margin-top: 1rem;
    }

    .trainer-name {
        font-size: 1.2rem;
        margin-bottom: 0.5rem;
    }

    .trainer-description {
        font-size: 1.08rem;
    }

    .trainer-name,
    .trainer-description {
        color: $main-dark;
    }

    .card-trainer {
        height: auto;
        padding: 1.5rem;
        margin-top: 15px;
        border-radius: 1.5rem;
        background-color: $light;
        transition: all 0.3s ease;

        &:hover {
            transform: translateY(-15px);
        }
    }

    .services-title {
        padding-inline: 2rem;
        margin: 5rem 0 2rem;
    }

    .grid-container {
        position: relative;
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 8rem;
    }

    .form-container {
        width: 40%;
        margin: 5rem 0;
    }

    .title-request {
        margin-bottom: 0.5rem;
        font-size: 1.5rem;
        color: $light;
    }

    .description-request {
        color: $gray;
    }

    .input-wrapper {
        position: relative;
        margin: 16px 0;

        label {
            position: absolute;
            top: 0.5rem;
            left: 0.5rem;

            color: $gray;
            transition: all 0.3s ease;
            pointer-events: none;
        }

        .input-name:focus + label,
        .input-name:not(:placeholder-shown) + label,
        .input-phone:focus + label,
        .input-phone:not(:placeholder-shown) + label {
            transform: translateY(-16px);
            font-size: 0.75rem;
            color: $accent-violet;
        }

    }

    .input-name,
    .input-phone {
        width: 40%;
        padding: 0.5rem;
        border: none;
        border-bottom: 2px solid $accent-violet;
        background: transparent;
        outline: none;
        caret-color: $light;
        color: $light;
    }

    .input-checkbox {
        margin-right: 0.5rem;
        
        accent-color: $accent-violet;
    }

    .label-checkbox {
        color: $gray;
    }
</style>