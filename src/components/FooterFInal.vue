<template>
    <footer>
        <h6>Stay In touch</h6>
        <div class="marquee-container">
            <div class="marquee">
                <div class="marquee__inner">
                    <span class="rolling"><a href="https://www.linkedin.com/in/mathias-quist-michaelsen-329590125/">LinkedIn</a></span>
                    <span class="rolling"><a href="https://www.instagram.com/mat.quist/">Instagram</a></span>
                    <span class="rolling"><a href="https://dribbble.com/MatQuist">Dribble</a></span>
                    <span class="rolling"><a href="https://www.nextlevelmedia.dk">NLM</a></span>
                    <span class="rolling"><a href="https://www.linkedin.com/in/mathias-quist-michaelsen-329590125/">LinkedIn</a></span>
                    <span class="rolling"><a href="https://www.instagram.com/mat.quist/">Instagram</a></span>
                    <span class="rolling"><a href="https://dribbble.com/MatQuist">Dribble</a></span>
                    <span class="rolling"><a href="https://www.nextlevelmedia.dk">NLM</a></span>
                </div>
            </div>
        </div>
        <h1>mathias.</h1>
    </footer>
</template>

<style scoped>
footer {
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    position: relative;
    left: -10%;
    width: 120%;
    height: 80vh;
    background-color: var(--main-black-color);
    overflow: hidden;
}

h1 {
    position: relative;
    top: 80px;
    filter: invert();
    font-size: 5rem;
}

h6 {
    color: #fff;
}

.marquee-container {
    position: relative;
    top: 10%;
    left: 100%;
    transform: translate(-50%, -50%);
    z-index: 1;
}
.rolling {
    font-family: sofia-pro, sans-serif;
    display: inline-block;
    position: relative;
    -webkit-text-fill-color: #fff;
    text-fill-color: #fff;
    color: #fff;
    transition: opacity 0.4s;
    font-weight: 900;
    line-height: 1.15;
    cursor: pointer;
}
.marquee {
    position: relative;
    overflow: hidden;
    z-index: 1;
    --offset: 80vw;
    --move-initial: calc(-25% + var(--offset));
    --move-final: calc(-75% + var(--offset));
}

.marquee__inner {
    width: fit-content;
    display: flex;
    position: relative;
    transform: translate3d(var(--move-inital), 0, 0);
    animation: marquee 15s linear infinite;
}

.marquee span {
    font-size: 6vw;
    padding: 0 2vw;
}

.marquee .marquee__inner {
    animation-play-state: running;
}
a{
    text-decoration: none;
    color: #fff;
}

@keyframes marquee {
    0% {
        transform: translate3d(var(--move-initial), 0, 0);
    }

    100% {
        transform: translate3d(var(--move-final), 0, 0);
    }
}
</style>