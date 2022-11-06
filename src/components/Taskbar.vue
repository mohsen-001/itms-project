<template>
    <div>
        

            <div class="task-bar">

                <div class="task-bar-header">
                    <span>{{ task_bar_header }}</span>
                    <div>
                        <p>{{ task_bar_count }}</p>
                    </div>
                </div>

                <div class="task-bar-body">

                    <button class="task-bar-add">+</button>

                    <div class="task-bar-holder">

                    </div>

                </div>
            </div>


    </div>
</template>

<script>
export default {
    name: "task-bar",
    props: ["task_bar_header", "task_bar_count"]
}
</script>

<style scoped>
.task-title {
    display: flex;
    margin: 40px 0 20px 0;
    color: white;
}

.task-bar {
    width: 100%;
    margin: 0 5px;
    padding: 5px;
    display: flex;
    flex-direction: column;
}

.task-bar .task-bar-header {
    background-color: #5F5F5F;
    display: flex;
    width: 100%;
    border-radius: 10px;
    color: white;
    padding: 8px 24px;
}

.task-bar .task-bar-header span {
    font-weight: 500;
}

.task-bar .task-bar-header div {
    margin-left: auto;
    background-color: rgba(255, 255, 255, 0.2);
    border-radius: 20px;
    padding: 2px 8px;
    font-size: 0.8rem;
}

.task-bar .task-bar-body {
    background-color: rgba(95, 95, 95, 0.15);
    height: 100%;
    margin-top: 10px;
    border-radius: 10px;
    padding: 10px;
    overflow: hidden;
}

.task-bar .task-bar-body .task-bar-add {
    width: 100%;
    color: white;
    font-size: 1.5rem;
    border-radius: 5px;
    background-color: rgba(255, 255, 255, 0.2);
    border: 2px solid rgba(255, 255, 255, 0.4);
    cursor: pointer;
}

.task-bar .task-bar-body .task-bar-add:hover {
    background-color: rgba(255, 255, 255, 0.5);
}

.task-bar .task-bar-body .task-bar-holder {
    width: 100%;
    height: 63vh;
    overflow: auto;
    margin-top: 10px;
    padding: 5px 5px;
}
</style>