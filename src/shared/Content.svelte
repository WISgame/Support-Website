<div class="container">
    <div class="content"><slot></slot></div>
</div>

<style>
    .content {
        width: clamp(45ch, 50%, 75ch);
    }

    .container {
        position: absolute;
        left: 0;
        top: 70%;
        width: 100%;
        display: flex;
        justify-content: center;
    }
</style>