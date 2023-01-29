<template>
    <div class="popup">
        <div class="popup-inner">
            <slot></slot>
            <button class="popup-close" @click="TogglePopup()">Close</button>
        </div>
    </div>
</template>


<script setup>

const props = defineProps(['TogglePopup'])

</script>


<style scoped>

.popup{

    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 99;
    border-color: rgba(0, 0, 0, 0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
}
.popup-inner{
    color: white;
    padding: 32px;
    background-color: rgb(116, 110, 110);
    text-align: start;
    font-size: 18px;
    border-radius: 15px;
}

.popup-close{
    text-align: center;
   margin-left: 80px;
   margin-top: 5px;
}

</style>
