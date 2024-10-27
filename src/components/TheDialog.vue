<template lang="">
    <teleport to="#dialog" :disabled="true">
        <div class="theDialog">
            <div class="theDialogContainer">
                <div class="dialog-header">
                    <h2>{{ title }}</h2>
                    <p>Are you sure you want to continue to the next page?</p>
                </div>
                <div class="dialog-content">
                    <slot></slot>
                </div>
                <div class="dialog-footer">
                    <slot name="footer"></slot>
                </div>
            </div>
        </div>
    </teleport>
</template>
<script>
export default {
    
}
</script>
<style  scoped>
    .theDialogContainer{
        position: fixed;
    top:50%;
    left:50%;
    right: 50%;
    bottom: 50%;
    background-color: #fff;
    width: 50%;
    max-width: 500px;
    height: 200px;
    padding: 20px;
    border-radius: 5px;
    transform: translate(-50%, -50%);
}
.theDialog{
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
    
}
.dialog-header{
    display: flex;
    justify-content: space-between;
}
.dialog-content{
    padding: 20px;
}
.dialog-footer{
    display: flex;
    justify-content: flex-end;
    padding: 10px;
}
</style>





