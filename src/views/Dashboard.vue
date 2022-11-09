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
                        <Taskbar task_bar_header="Todo" :task_bar_count="task.length" :no_task="emptyTask[0]"
                            task_type="todo" @addClickBtn="addTask(task)">
                            <Task :task="task" />

                        </Taskbar>

                        <!-- inprogress -->
                        <Taskbar task_type="inprogress-theme" task_bar_header="Progress" :no_task="emptyTask[1]"
                            :task_bar_count="task1.length" @addClickBtn="addTask(task1)">
                            <Task :task="task1" />
                        </Taskbar>

                        <!-- completed -->
                        <Taskbar task_type="done-theme" task_bar_header="Completed" :no_task="emptyTask[2]"
                            :task_bar_count="task2.length" @addClickBtn="addTask(task2)">
                            <Task :task="task2" />

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
            taskName: '',
            task: [],
            task1: [],
            task2: [],
            emptyTask: [true, true, true],
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
        },


        checkEmptyTask() {
            const holder = document.querySelectorAll('.task-bar-holder');
            // const holderArr = [...holder]
            console.log(holder.length);
            this.emptyTask = [];

            holder.forEach(item => {
                if (item.children.length - 2 <= 0) {
                    this.emptyTask.push(true);
                    console.log(item.children, "first");
                } else {
                    this.emptyTask.push(false);
                    console.log(item.children.length, "second");
                }
            })

            console.log(this.emptyTask);
            // const toDoHolderChild = document.querySelector('#todo .task-bar-holder').children;
            // const inprogressHolderChild = document.querySelector('#inprogress-theme .task-bar-holder').children;
            // const doneHolderChild = document.querySelector('#done-theme .task-bar-holder').children;
            // if (toDoHolderChild <= 2) {
            //     this.emptyTask = true;
            // }else {
            //     this.emptyTask = false;
            // }
        },

        addTask(taskName) {
            
            taskName.unshift(
                {
                    subject: "Subject of the task1",
                    body: "Lorem ipsum dolor, ",
                    date: "2022-01-10",
                    time: "16:30",
                });

                this.checkEmptyTask();
            
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

#content {
    display: flex;
    justify-content: center;
    align-items: center;
}

.task-container {
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
