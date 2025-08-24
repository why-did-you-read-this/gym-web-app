<template>
    <header class="header">
        <div class="header-wrapper">
            <div class="content">
                <h2 class="title">Gym App</h2>
                <p class="subtitle">Приложение для тренировок</p>
            </div>

            <nav class="menu">
                <ul class="menu-list">
                    <li class="menu-item">
                        <a class="menu-link" href="#">Главная</a>
                    </li>
                    <li class="menu-item">
                        <a class="menu-link" href="#">Расписание</a>
                    </li>
                    <li class="menu-item">
                        <a class="menu-link" href="#">Услуги</a>
                    </li>
                    <li class="menu-item">
                        <a class="menu-link" href="#">О нас</a>
                    </li>
                </ul>
            </nav>

            <div class="user-tools">
                <div class="phone-wrapper">
                    <img class="phone-icon" 
                         src="../assets/icons/phone.png" 
                         alt="Phone icon" 
                         width="25"
                         height="25"
                        >
                    <a class="phone-link" href="#">+7 123 456 78 91</a>
                </div>
                <a class="login-link" href="#">
                    <img class="user-icon" 
                         src="../assets/icons/user.png" 
                         alt="User login" 
                         width="35" 
                         height="35"
                        >
                </a>
            </div>
        </div>
    </header>
</template>

<script>

</script>

<style lang="scss" scoped>
    .header {
        position: sticky;
        top: 0;
        z-index: 1;
        width: 100%;
        padding: 0.25rem;
        margin-bottom: 0.5rem;
        background-color: $main-dark;
        box-shadow: 0 10px 6px rgba(0, 0, 0, 0.3);
    }

    .header-wrapper {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 80%;
        margin: 1.25rem auto;
        padding-inline: 0.5rem;
    }

    .content {
        display: flex;
        flex-direction: column;
        gap: 0.25rem;
    }

    .title {
        font-size: 1.5rem;
        font-weight: bold;
        color: $accent-violet;
    }

    .subtitle {
        color: $gray;
    }

    .menu-list {
        display: flex;
        gap: 0.75rem;
        list-style: none;
    }

    .menu-item {
        margin: 0 1rem;
    }

    .menu-link {
        position: relative;
        padding: 0.3rem;
        text-decoration: none;
        color: $gray;

        &:hover {
            color: $light;
        }
    }
    
    .menu-link::before {
        content: "";
        position: absolute;
        inset: auto auto 0 0;
        width: 0;
        height: 2px;
        background: $gradient-violet;
        background: linear-gradient(to right, $gradient-blue, $gradient-violet);
        transition: width 0.3s ease;
    }

    .menu-link:hover::before {
        width: 100%;
    }

    .user-tools {
        display: flex;
        gap: 1.75rem;
    }

    .phone-wrapper {
        display: flex;
        align-items: center;
        gap: 0.75rem;
    }

    .phone-link {
        text-decoration: none;
        color: $gray;

        &:hover {
            color: $light;
        }
    }
</style>