<template>
    <div class="container" :class="closeModel?'close-model':''">
        <div class="content">
            <input type="text">
            <textarea name="textarea" id="textArea" cols="30" rows="10"></textarea>
            <button>Add</button>
        </div>
        
    </div>
</template>

<script>
export default {
    data() {
        return {
            closeModel : true,
        }
    },
    methods: {
        closeIt() {
            this.closeModel = !this.closeModel;
        }
    }
}
</script>

<style scope>

.close-model {
    display: none !important;
}
.container {
    width: 100vw;
    height: 100vh;
    background-color: rgba(0, 0, 0, .5);
    position: fixed;
    z-index: 10;
    display: flex;
    justify-content: center;
    align-items: center;
}

.content {
    width: 400px;
    height: auto;
    padding: 20px;
    background-color: white;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.content input {
    margin: 10px 0;
}
</style>