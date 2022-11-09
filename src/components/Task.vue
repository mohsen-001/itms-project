<template>
    <div>
        <div class="task-bar-item">
            <div class="task-bar-item-subject">
                <i class="fa-solid fa-grip"></i>
                <div class="subject">Subject of the task</div>
                <i class="fa-solid fa-up-right-from-square"></i>
            </div>
            <div class="task-bar-item-body">
                Lorem ipsum dolor, sit amet consectetur adipisicing elit.
            </div>
            <div class="task-bar-item-date">
                <span class="update-date">2022-01-10</span>
                <span class="update-time">16:30</span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "task-item",
    data() {
        return {
            
        }
    },
    methods: {}
}
</script>

<style scoped>

#right_click{
    background-color: white;
    display: inline-block;
    padding: 5px 5px;
    border-radius: 10px;
}

#right_click li {
    list-style: none;
    padding: 10px 30px 10px 10px;
    border-radius: 5px;
    cursor: pointer;
}

#right_click li:hover {
    background-color: var(--secondary-color-hover);
    color: var(--primary-color);
}

.showIt {
    display: block;
}
.task-bar-item{
    background-color: white;
    border-radius: 5px;
    padding: 12px;
    margin: 10px 0;
}

/* .task-bar-item:last-child, .task-container .task-bar .task-bar-body .task-bar-item:first-child {
    margin: 0 0 !important;
} */

.task-bar-item .task-bar-item-subject {
    width: 100%;
    display: flex;
    align-items: center;
    padding: 5px 0;
}

.task-bar-item .task-bar-item-subject .fa-grip {
    font-size: 1.3rem;
    opacity: 0.5;
}

.task-bar-item .task-bar-item-subject .fa-up-right-from-square{
    color: var(--primary-color);
    display: none;
}

.task-bar-item .task-bar-item-subject .subject {
    font-size: 1rem;
    font-weight: 600;
    margin: 0 8px 0 14px;
    cursor: pointer;
}

.task-bar-item .task-bar-item-subject .subject:hover .task-bar-item .task-bar-item-subject .fa-up-right-from-square{
    display: block !important;
}

.task-bar-item .task-bar-item-body{
    font-size: 0.8rem;
    background-color: rgba(95, 95, 95, 0.1);
    padding: 10px;
    border-radius: 5px;
    margin-top: 10px;
}

.task-bar-item .task-bar-item-date {
    display: flex;
    padding: 10px 0 0 0;
}

.task-bar-item .task-bar-item-date span{
    font-size: 0.8rem;
    opacity: 0.5;
}

.task-bar-item .task-bar-item-date .update-date {
    margin-left: auto;
    margin-right: 20px;
}

.task-bar-item .task-bar-item-date .update-time {
    position: relative;
}

.task-bar-item .task-bar-item-date .update-time::before {
    content: '';
    width: 5px;
    height: 5px;
    background-color: black;
    position: absolute;
    border-radius: 25px;
    top: 50%;
    left: -13px;
    transform: translateY(-50%);
}
</style>