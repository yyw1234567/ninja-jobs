<template>
    <div>
        <div id="nav">
            <router-link to="/">Home</router-link> |
            <router-link :to="{ name: 'About' }">About</router-link>
            <router-link :to="{ name: 'jobs' }">Jobs</router-link>
        </div>
        <router-view />

        <button @click="redirect">Redirect</button>
        <button @click="back">Go back</button>
        <button @click="forward">Go forward</button>
    </div>
</template>

<script>
    export default {
        methods: {
            redirect() {
                this.$router.push({ name: 'home'})
            },

            back() {
                this.$router.go(-1)
            },

            forward() {
                this.$router.go(1)
            }
        }
    }
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

#nav {
    padding: 30px;
}

#nav a {
    font-weight: bold;
    color: #2c3e50;
}

#nav a.router-link-exact-active {
    color: white;
    background: rgb(236, 67, 112);
    border: none;
    padding: 15px;
    border-radius: 5px;
    font-size: 20px;
}

button{
    margin: 0 10px;
    padding: 10px;
    border: none;
    border-radius: 4px;
}
</style>
