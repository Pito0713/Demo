<template>
<div></div>
</template>

<script>

</script>

<style scoped lang="scss">
.sciocal{
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 5vw;
    border-bottom: 2px solid var(--border-color);
    i{
        font-size: 7vw;
    }
    a{
        font-size: 6vw;
        padding: 1vw;
    }
    button{
        font-size: 5vw;
        color: var(--text-color);
        border: none;
        background-color: var(--bottom-color);
        animation-name:attention;
        animation-duration:4s;
        animation-iteration-count:infinite;
    }
}

.my-2{
    margin: 0 4vw;
}
@keyframes attention{
    0%{
        transform: rotate(0deg);
    }
    33%{
        transform: rotate(5.6deg);
    }
    66%{
        transform: rotate(-5.6deg);
    }
    100%{
        transform: rotate(0deg);
    }
}

</style>
