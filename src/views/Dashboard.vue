<template>
    <div>
        <div id="container">
            <div id="sidebar">
                <Sidebar ref="navbar" />
            </div>
            <div id="content-container">
                <Navbar @toggle="toggleSidebar" />
                <div id="content">
                    <div class="task-container">

                        <!-- TODO -->
                        <Taskbar task_bar_header="Todo" :task_bar_count="task_todo_count">
                            <Task />
                            <Task />

                        </Taskbar>

                        <!-- inprogress -->
                        <Taskbar task_type="inprogress-theme" task_bar_header="Progress"
                            :task_bar_count="task_progress_count">
                            <Task />
                        </Taskbar>

                        <!-- completed -->
                        <Taskbar task_type="done-theme" task_bar_header="Completed"
                            :task_bar_count="task_complete_count">
                            <Task />
                            <Task />
                            <Task />
                        </Taskbar>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Sidebar from '@/components/Sidebar.vue';
import Navbar from '../components/Navbar.vue';
import Taskbar from '../components/Taskbar.vue';
import Task from '../components/Task.vue';

export default {
    name: "Dashboard-page",
    data() {
        return {
            task_todo_count: '0',
            task_progress_count: '0',
            task_complete_count: '0',
        }
    },
    components: {
        Sidebar,
        Navbar,
        Taskbar,
        Task,
    },
    methods: {
        toggleSidebar() {
            this.$refs.navbar.collapsSidebar()
        }
    },
};
</script>

<style scoped>
#content-container {
    background: url(../assets/content-bg.jpg) no-repeat;
    background-size: cover;
    width: 100%;
    padding: 20px 60px;

}

#container {
    width: 100%;
    height: 100vh;
    display: flex;
}

#navbar {
    background-color: rgb(255, 203, 107);
}

/* #content {
    background-color: rgb(129, 129, 129);
} */

.task-container {
    width: 100%;
    height: auto;
    background-color: rgba(255, 255, 255, 0.1);
    border-radius: 20px;
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    padding: 14px 10px;
    display: flex;
    justify-content: space-between;
    margin-top: 25px;
}

.task-container>* {
    flex: 1;
    margin: 0 10px;
}
</style>
