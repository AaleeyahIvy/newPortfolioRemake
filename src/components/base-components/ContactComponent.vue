<template>
    <div class="outer-card">
        <div class="inner-card">
            <h3>Reach out!</h3>
            <div>⊹ ₊  ⁺‧₊˚ ♡ ପ(๑•ᴗ•๑)ଓ ♡˚₊‧⁺ ₊ ⊹</div>
            <div>Phone: 513-376-5017</div>
            <div>Email: <a href="mailto:samanthastar87@gmail.com">samanthastar87@gmail.com</a></div>
            <div>Discord: @aaleeyah</div>
            <h3>I game too!</h3>
            <div>⊹ ₊✧(⸝⸝⸝ᵒ̴̶̷ ｡ ᵒ̴̶̷⸝⸝⸝)✧₊ ⊹</div>
            <div>League Of Legends</div>
            <div>Valorant</div>
            <div>Overwatch 2</div>
            <div>COD, and Fortnite</div>
        </div>
    </div>
</template>
<script>
import VanillaTilt from 'vanilla-tilt';
export default {
    name: 'ContactComponent',
    data() {
        return {
            aboutpage: 'This is the Contact page'
        }
    },
    mounted(){
        const tilt = document.querySelector(".outer-card");
         VanillaTilt.init(tilt, {
            max: 25,
            speed: 400,
            glare: true,
        });


    }
}
</script>
<style>
.outer-card {
    margin: auto;
    padding: auto;
    width: 300px;
    height: 300px;
    background: rgb(255, 192, 217);
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    transform-style: preserve-3d;
    transform: perspective(500px);
}
.inner-card {
    width: 300px;
    height: 300px;
    color: var(--main-text-color);
    background-color: #ffffff47;
    border-radius: 10px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    transform: translateZ(5px);
}
</style>