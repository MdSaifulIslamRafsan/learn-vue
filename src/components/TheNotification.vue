<template>
    <teleport to='#notification'>
        <div class="notification-container">
            <div class="notification">
                <div class="notification-message">
                    {{ message }}
                </div>
            </div>
        </div>
    </teleport>
</template>
<script>
export default {
    props: ["message"]
}
</script>
<style scoped>

    .notification-container{
        position: fixed;
        top: 0;
        left: 0;
        width: 500px;
        height: 60px;
        background-color: rgba(0, 0, 0, 0.5);
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .notification{
        width: 300px;
        background-color: white;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    }
    .notification-message{
        font-size: 20px;
    }

</style>