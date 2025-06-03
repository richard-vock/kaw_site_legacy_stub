<script lang="ts">
    import logo from '$lib/images/kaw-font-white.svg';
</script>
<div class="main-bg">
    <div class="splash-logo">
        <h1>Kulturausbesserungswerk</h1>
        <img src={logo} class="center-logo" alt="KAW" />
        <h1>Autonomes Zentrum für Kultur & Politik</h1>
        <h1>in Leverkusen - Opladen</h1>
    </div>
</div>

<style>
div.main-bg {
    display: flex;
    width: 100%;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    background: url($lib/images/home-bg.jpg);
    background-repeat: no-repeat;
    background-position: 50% 100%;
    background-size: cover;
    background-clip: border-box;
}

@media only screen and (min-width: 2560px) {
    div.main-bg {
        min-height: 105vh;
    }
}

div.splash-logo {
    width: 100%;
    max-width: 1280px;
    display: flex;
    flex-direction: column;
    align-items: center;
    background: url($lib/images/home-header-splash.png);
    background-repeat: no-repeat;
    background-position: 50% 50%;
    background-size: cover;
    padding: 135px 0;
    overflow: hidden;
    /* min-width: 683px; */
}

@media only screen and (min-width: 652px) {
    div.splash-logo {
        background-size: contain;
    }
}

img.center-logo {
    display: block;
    width: 300px;
    height: 60px;
}

div.splash-logo h1 {
    display: block;
    color: #ffffff;
    font-family: var(--running-font);
    font-size: 16px;
    font-weight: 300;
    text-transform: none;
    text-align: center;
}

@media only screen and (min-width: 375px) {
    div.splash-logo h1 {
        font-size: 18px;
    }
}

@media only screen and (min-width: 425px) {
    div.splash-logo h1 {
        font-size: 20px;
    }
}
</style>
