<template>
    <div>


        <div class="task-bar" :id="task_type">

            <div class="task-bar-header">
                <span>{{ task_bar_header }}</span>
                <div>
                    <p>{{ task_bar_count }}</p>
                </div>
            </div>

            <div class="task-bar-body">

                <button @click="$emit('addClickBtn')" class="task-bar-add">+</button>
                <!-- :class="no_task ? 'noTask' : ''" -->

                <div class="task-bar-holder" >
                    <p class="no_task_text">No Task</p>
                    <slot></slot>
                </div>

            </div>
        </div>


    </div>
</template>

<script>
export default {
    data() {
        return {
            // taskChilds: 0,
        }
    },

    name: "task-bar",

    props: ["task_bar_header", "task_bar_count", "task_type", "no_task"],

    

    methods: {
        // checkChild() {
        //     const holder = document.querySelector('.task-bar-holder div');
        //     const holderArr = [...holder];
           
        //         if (holder.length == 0) {
        //             this.emptyTask.push(true);
        //             // console.log(item.children.length, "first");
        //         } else {
        //             this.emptyTask.push(false);
        //             // console.log(item.children.length, "second");
        //         }
           
        // }
    }


}
</script>

<style scoped>
.no_task_text {
    display: none;
}

.noTask {
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    opacity: .9;
    font-weight: 100;
}

.noTask .no_task_text {
    display: block;
}



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
    min-width: 400px;
    /* max-width: 500px; */
    height: 65vh;
    overflow: auto;
    margin-top: 10px;
    padding: 5px 5px;

}

.task-bar .task-bar-body .task-bar-holder>* {
    margin: 10px 0;
}

.task-bar .task-bar-body .task-bar-holder:last-child,
.task-bar .task-bar-body .task-bar-holder:first-child {
    margin: 0 0 !important;
}


/* inprogress-theme */

#inprogress-theme .task-bar-header {
    background-color: var(--primary-color) !important;
}

#inprogress-theme :deep(.task-bar-item-subject) .fa-grip {
    color: var(--primary-color);
}

#inprogress-theme :deep(.task-bar-item-body) {
    background-color: rgba(71, 181, 255, 0.1);
}

/* inprogress-theme */

#done-theme .task-bar-header {
    background-color: #2EB100 !important;
}

#done-theme :deep(.task-bar-item-subject) .fa-grip {
    color: #2EB100;
}

#done-theme :deep(.task-bar-item-body) {
    background-color: rgba(46, 177, 0, 0.1);
}



/* scroll bar style */

::-webkit-scrollbar {
    width: 3px;
}

::-webkit-scrollbar-track {
    background-color: rgba(255, 255, 255, 0.1);
    border-radius: 5px;
    margin-left: 5px;
}

::-webkit-scrollbar-thumb {
    background-color: rgba(255, 255, 255, 1);
    border-radius: 5px;
}
</style>