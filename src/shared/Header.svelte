<div class="header"><slot></slot></div>
<div class="wave"></div>

<style>
    .header {
        position: absolute;
        width: 100%;
        height: 60%;
        top: 0;
        left: 0;
        background-image: url("Background.png");
        display: flex;
        justify-content: center;
        font-size: 2rem;
        color: #fff;
        padding: 1em;
        box-sizing: border-box;
    }

    .wave {
        position: absolute;
        top: 1px;
        left: 0;
        width: 100%;
        height: 60%;
        background-image: url("wave.svg");
        background-position-x: center;
        background-position-y: bottom;
        background-size: cover;

    }
</style>