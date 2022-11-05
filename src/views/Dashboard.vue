<template>
    <div>
        <div id="container">
            <div id="sidebar">
                <Sidebar />
            </div>
            <div id="content-container">
                <!-- <div id="navbar">navbar</div>
                <div id="content">content</div> -->
            </div>
        </div>
    </div>
</template>

<script>
import Sidebar from '@/components/Sidebar.vue';
export default {
    name: "Dashboard-page",
    components: {
        Sidebar,
    }
};
</script>

<style scoped>

#content-container{
    background: url(../assets/content-bg.jpg) no-repeat;
    background-size: cover;
    width: 100%;
}

#container {
    width: 100%;
    height: 100vh;
    display: flex;
}

#navbar {
    background-color: rgb(255, 203, 107);
}

#content {
    background-color: rgb(129, 129, 129);
}

</style>
