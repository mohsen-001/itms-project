<template>
    <div>
        <div class="navbar">
            <Button @check="clickable" v-html="menu_icon" class="g-btn g-btn-tertiary bar-icon" />
            <span class="time">{{ time }}</span>
            <span class="date">{{ date }}</span>
            <div class="searchbox">
                <input type="text" placeholder="Search tasks...">

                <Button v-html="search_icon" class="g-btn g-btn-tertiary search-icon" />
            </div>
        </div>
    </div>
</template>

<script>
import Button from '../components/Button.vue';

export default {
    name: 'nav-bar',
    components: {
        Button,
    },
    data() {
        return {
            search_icon: '<i class="fa-solid fa-magnifying-glass"></i>',
            menu_icon: '<i class="fa-solid fa-bars-staggered"></i>',
            time: '05:30',
            date: 'Wed, Oct 6'
        }
    },
    methods: {
        clickable() {
            this.$emit('toggle')
        },
    }
}
</script>

<style scoped>
.navbar {
    /* padding: 0px 60px; */
    display: flex;
    align-items: center;
}

.navbar .bar-icon {
    padding: 14px;
    margin-right: 30px;
    color: white;
    font-weight: bold;
    font-size: 1.7rem;
}

.navbar .bar-icon:hover {
    background-color: rgba(255, 255, 255, 0.2);
}

.navbar .time,
.date {
    font-size: 2.1rem;
    font-weight: 200;
    color: white;
    margin: 0 15px;
}

.navbar .date {
    position: relative;
}

.navbar .date::before {
    content: "";
    position: absolute;
    width: 8px;
    height: 8px;
    background-color: white;
    border-radius: 50px;
    left: -20px;
    top: 50%;
    transform: translateY(-50%);
}

.searchbox {
    margin-left: auto;
    position: relative;
}

.searchbox input {
    width: 400px;
    border: none;
    border-radius: 50px;
    height: 50px;
    background-color: rgba(255, 255, 255, 0.5);
    padding: 20px;
}

.searchbox input:focus {
    outline: 2px solid white;
}

.searchbox .search-icon {
    padding: 12px;
    border-radius: 50px;
    color: rgb(32, 32, 32);
    position: absolute;
    right: 7px;
    top: 4px;
}

.navbar .search-icon:hover {
    background-color: var(--primary-color);
    color: white;
}
</style>