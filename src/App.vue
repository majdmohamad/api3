<template>
    <nav>
        <div class="container">
            <div class="logo">Vue Test</div>
            <router-link to="/">Home</router-link>
            <router-link to="/about">About <span>|</span></router-link>
            <router-link to="/help">Help <span>|</span></router-link>
            <router-link to="/blog">Blog <span>|</span></router-link>
        </div>
    </nav>
    <router-view />
</template>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

nav {
    padding: 25px;
    padding-bottom: 45px;
    background-color: #333;

    .logo {
        font-size: 24px;
        float: left;
        width: 200px;
        color: #fff;
    }

    a {
        font-weight: bold;
        color: #fff;
        float: right;
        padding-right: 10px;
        text-decoration: none;

        span {
            color: #fff !important;
        }

        &.router-link-exact-active {
            color: #42b983;
        }
    }
}
</style>
