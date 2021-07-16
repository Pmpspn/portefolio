<template>
  <div class="container">
    <p class="text-center mt-20 text-white text-xl">
      <span class="text-center mt-20 text-white text-2xl typed-text">{{ typeValue }}</span>
      <span class="typed-cursor" :class="{'typing': typeStatus}">_</span>
    </p>
  </div>
</template>

<script>

export default {
  data: () => {
    return {
      typeValue: '',
      typeStatus: false,
      typeArray: ['Ludovic Spina', 'développeur', 'passionné'],
      typingSpeed: 200,
      erasingSpeed: 100,
      newTextDelay: 2000,
      typeArrayIndex: 0,
      charIndex: 0,
    }
  },
  methods: {
    typeText() {
      if (this.charIndex < this.typeArray[this.typeArrayIndex].length) {
        if (!this.typeStatus)
          this.typeStatus = true;
        this.typeValue += this.typeArray[this.typeArrayIndex].charAt(this.charIndex);
        this.charIndex += 1;
        setTimeout(this.typeText, this.typingSpeed);
      } else {
        this.typeStatus = false;
        setTimeout(this.eraseText, this.newTextDelay);
      }
    },
    eraseText() {
      if (this.charIndex > 0) {
        if (!this.typeStatus)
          this.typeStatus = true;
        this.typeValue = this.typeArray[this.typeArrayIndex].substring(0, this.charIndex - 1);
        this.charIndex -= 1;
        setTimeout(this.eraseText, this.erasingSpeed);
      } else {
        this.typeStatus = false;
        this.typeArrayIndex += 1;
        if (this.typeArrayIndex >= this.typeArray.length)
          this.typeArrayIndex = 0;
        setTimeout(this.typeText, this.typingSpeed + 1000);
      }
    }
  },
  created() {
    setTimeout(this.typeText, this.newTextDelay + 200);
  }
}

</script>


<style scoped>

span.typed-text {
  color: #cdcdcd;
}

span.typed-cursor {
  color: rgba(128, 128, 128, 0.65);
  animation: cursorBlink 1s infinite;
}

span.cursor.typing {
  animation: none;
}

@keyframes cursorBlink {
  20% {
    color: rgba(128, 128, 128, 0.65);
  }
  50% {
    color: transparent
  }
  50% {
    color: transparent
  }
}
</style>