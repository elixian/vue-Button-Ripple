<template>
  <button class="btn">Valider</button>
</template>

<script>
export default {
  mounted() {
    const btns = document.querySelectorAll('.btn');
    btns.forEach((btn) => {
      btn.addEventListener('click', function (e) {
        let x = e.clientX - e.target.offsetLeft;
        let y = e.clientY - e.target.offsetTop;

        //add ripple
        let ripples = document.createElement('span');
        ripples.classList.add('ripple');
        ripples.style.left = `${x}px`;
        ripples.style.top = `${y}px`;
        this.appendChild(ripples);

        setTimeout(() => {
          ripples.remove();
        }, 1000);
      });
    });
  },
  setup() {
    return {};
  },
};
</script>

<style lang="scss">
.btn {
  font-family: 'Poppins', sans-serif;
  position: relative;
  font-size: 18px;
  padding: 10px;
  min-width: 120px;
  border-radius: 8px;
  background: #467ff7;
  border: none;
  overflow: hidden;
  cursor: pointer;
  .ripple {
    position: absolute;
    display: block;
    transform: translate(-50%, -50%);
    pointer-events: none;
    border-radius: 100%;
    background: white;
    animation: ripple-anime 0.8s linear forwards;
  }
}

@keyframes ripple-anime {
  0% {
    width: 0;
    height: 0;
    opacity: 0.5;
  }
  100% {
    width: 400px;
    height: 400px;
    filter: blur(6px);
    opacity: 0;
  }
}
</style>
