<script>
export default {
    data() {
        return {
            hexColor: null
        }
    },
    methods: {
        updateBackgroundColor() {
            const date = new Date();
            let hours = date.getHours();
            let minutes = date.getMinutes();
            let seconds = date.getSeconds();

            hours = hours.toString().length === 1 ? '0' + hours : hours;
            minutes = minutes.toString().length === 1 ? '0' + minutes : minutes;
            seconds = seconds.toString().length === 1 ? '0' + seconds : seconds;

            document.body.style.backgroundColor = this.hexColor = '#' + hours + minutes + seconds;
        }
    },
    created() {
        this.updateBackgroundColor();
    },
    mounted: function() {
        setInterval(this.updateBackgroundColor, 1000)
    }
}
</script>

<template>
    <div class="container">
        <h1 id="clock">{{hexColor}}</h1>
    </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Exo+2:wght@100&display=swap');

.container {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
#clock {
    font-family: 'Exo 2', sans-serif;
    font-size: 100px;
    color: white;
}
</style>