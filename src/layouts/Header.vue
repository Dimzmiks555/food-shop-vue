<template>
    <header>
        <div class="user">
            <div class="image">
                <img src="https://steamuserimages-a.akamaihd.net/ugc/1815514859111615086/C25F8CF5F42A932AC1E30D33D2956A205EB9CF42/?imw=512&amp;imh=512&amp;ima=fit&amp;impolicy=Letterbox&amp;imcolor=%23000000&amp;letterbox=true">
            </div>
            <p>
                Афанасьев Николай
            </p>
        </div>
        <nav>
            <ul>
                <router-link to="/"><li><i><img src="https://api.iconify.design/akar-icons/home.svg"></i><span>Главная</span></li></router-link>
                <router-link to="/menu"><li><i><img src="https://api.iconify.design/ep/menu.svg"></i><span>Меню</span></li></router-link>
                <router-link to="/articles"><li><i><img src="https://api.iconify.design/ic/outline-article.svg"></i><span>Статьи</span></li></router-link>
                <router-link to="/settings"><li><i><img src="https://api.iconify.design/ci/settings.svg"></i><span>Настройки</span></li></router-link>
            </ul>
        </nav>
    </header>
</template>

<script>
    export default {
        name: 'Header'
    }
</script>

<style scoped>


    .router-link-exact-active li{
        background: #f8a ;
    }

    header {
        width: 300px;
        /* margin-right: 40px; */
        padding: 40px 0;
        display: flex;
        flex-direction: column;
        /* align-items: center; */
    }

    .user {
        width: 100%;
        padding: 20px 0;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .user .image {
        height: 100px;
        width: 100px;
        margin-bottom: 20px;
        border-radius: 20px;
        overflow: hidden;
        padding: 10px;
        background: #fff;
    }

    .user .image img {
        border-radius: 14px;
        width: auto;
        height: 100%;

    }

    .user p {
        font-size: 18px;
        font-weight: 900;

    }

    nav {
        padding: 0 40px 0 0;
    }

    ul li {
        border-radius: 20px;
        margin-bottom: 20px;
        display: flex;
        align-items: center;
        cursor: pointer;
        user-select: none;
    }

    ul a {
        text-decoration: none;
        color: #333;
    }

    ul li:hover {
        background: #fac;
    }


    ul li i {
        padding: 16px;
        display: block;
        width: 60px;
        height: 60px;
        background: #fff;
        border-radius: 20px;
    }
    ul li i img {
        height: 100%;
        width: auto;
    }
    ul li span {
        display: block;
        border-radius: 20px;
        padding: 10px 30px;
    }

</style>