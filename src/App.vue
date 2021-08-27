<template>
    <div id="app">
        <div id="nav">
            <router-link to="/" class="p-1">Home</router-link>
            <router-link to="/about" class="p-1">About</router-link>
            <template v-if="!authenticated">
                <router-link to="/dang-nhap" class="p-1">Đăng nhập</router-link>
            </template>
            <template v-else>
                <router-link to="/tai-khoan">{{ user.name }}</router-link>
                <router-link to="#" class="p-1">Đăng xuất</router-link>
            </template>
        </div>
        <router-view />
    </div>
</template>

<script>
import { mapState } from "vuex";
export default {
    computed: {
        ...mapState({
            authenticated: "auth/authenticated",
            user: "auth/user",
        }),
    },
};
</script>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
}
#nav {
    padding: 30px;
    text-align: center;
    a {
        font-weight: bold;
        color: #2c3e50;
        text-decoration-line: none;
        &.router-link-exact-active {
            color: #42b983;
        }
    }
}
</style>