<script>
import NewIssues from './components/NewIssues.vue';
import ArchivedIssues from './components/ArchivedIssues.vue';
import CurrentIssues from './components/CurrentIssues.vue';

export default {
    name: '#app',
    components: {
        CurrentIssues,
        ArchivedIssues,
        NewIssues,
    },
    data() {
        return {
            component: '',
        }
    },
    mounted() { },
    methods: {
        hideMenu() {
            document.querySelector("#menu").style.display = 'none'
        },
        showMenu() {
            document.querySelector("#menu").style.display = 'flex'
        },
    }
}
</script>

<template>
    <div class="header">
        <button v-if="component != ''" @click="this.component=''; this.showMenu()">
            <!-- <i class="fa-solid fa-angles-left"></i> -->
            <span>&laquo;</span>
        </button>
        <span v-else>Главная</span>
        <!-- <button class="reload" @click="reload()">
            <i class="fa-solid fa-rotate-right"></i>
        </button> -->
    </div>
    <div class="menu" id="menu" style="display: flex">
        <button type="button" @click="this.component = 'CurrentIssues'; this.hideMenu()">Текущие задачи</button>
        <button type="button" @click="this.component = 'NewIssues'; this.hideMenu()">Новые задачи</button>
        <button type="button" @click="this.component = 'ArchivedIssues'; this.hideMenu()">Архив задач</button>
    </div>

    <component :is="this.component"></component>
</template>

<style scoped>
.header {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: 100vw;
    height: 8vh;
    background-color: #213547;
    text-align: left;
}

.header span {
    font-size: 1.4rem;
    font-weight: 600;
    color: #ffffff;
    margin-left: 1.5rem;
}

.header button {
    width: 10vh;
    height: 8vh;
    border: none;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: #f8f9fa;
    font-size: 2rem;
    font-weight: 600;
    background-color: #213547;
    transition: background-color 150ms;
}

.header button span {
    margin: -0.2rem 0 0 0;
    font-weight: 900;
}

.menu {
    width: 84%;
    max-height: 92vh;
    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;
    /* justify-content: center; */
    gap: 10%;
    position: absolute;
    top: 8vh;
    left: 0;
    margin: 8%;
}

.menu button {
    width: 45%;
    aspect-ratio: 1/1;
    font-size: 1.2em;
    margin-bottom: 10%;
}
</style>
