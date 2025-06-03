<script lang="ts">
    import { page } from '$app/stores';
    import logo from '$lib/images/kaw_logo_menu.svg';
</script>

<nav>
    <a href="/" aria-current={$page.url.pathname === '/' ? 'page' : undefined}>Startseite</a>

    <img alt="KAW" src={logo} class="menu-logo" />

    <a href="/veranstaltungen" aria-current={$page.url.pathname.startsWith('/veranstaltungen') ? 'page' : undefined}>Veranstaltungen</a>
</nav>

<style>
    nav {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        column-gap: 1.5em;
    }

    nav a {
        display: none;
        padding: 5px 0;
        color: var(--dark-grey);
        text-transform: uppercase;
        font-family: var(--heading-font);
        font-size: 11px;
        font-weight: 700;
        text-decoration: none;
        letter-spacing: 1.8px;
        border-bottom: 1px solid rgba(0,0,0,0); /* prevents resize when active */
    }

    nav img.menu-logo {
        position: absolute;
        left: 20px;
        height: 40px;
    }

    @media only screen and (min-width: 768px) {
        nav a {
            display: block;
        }
        nav img.menu-logo {
            position: relative;
            left: 0px;
            display: block;
        }
    }

    nav a[aria-current='page'] {
        border-bottom: 1px solid var(--primary);
    }

    nav a:hover {
        color: var(--primary);
    }

</style>
