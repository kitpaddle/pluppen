<template>
  <div class="container">
    <h1>💕 PLUPPEN 💕</h1>
    
    <p class="compliment">
      Hej sötis, hoppas du har en bra första dag tillbaka på jobbet.<br><br>Du är allt jag någonsin drömt om.<br>Du är pilgrimen som leder mig till äventyr, till nya smaker, nya tankar och nya vyer. Du ser på världen som en lekplats att uppleva och utforska. Dina ögon skimrar med glädje för det okända och din själ brinner varmt för livet och kärlek. Varje stund med dig är en gåva och ett äventyr.<br><br>Du är i din helhet - din fysik, din personlighet, dina svagheter och styrkor; den vackraste och mest underbara person jag haft privilegiet att lära känna.
    </p>
    
    <p class="question">Vill du ses på Valentine?</p>
    
    <div class="buttons">
      <button id="yesBtn" @click="onYes">Ja! 💕</button>
      <button id="noBtn" @mousemove="moveButton">Nej</button>
    </div>
    
    <p v-if="hasClickedYes" class="success-message">
      🎉 Du gör mig lyckligare än någonsin! 💕
    </p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      hasClickedYes: false
    }
  },
  methods: {
    onYes() {
      this.hasClickedYes = true
      this.createHearts()
    },
    moveButton() {
      const noBtn = document.getElementById('noBtn')
      const container = document.querySelector('.container')
      
      // Get container bounds
      const containerRect = container.getBoundingClientRect()
      const containerWidth = containerRect.width
      const containerHeight = containerRect.height
      
      // Button dimensions
      const btnWidth = 80
      const btnHeight = 45
      
      // Generate random position within container
      const randomX = Math.random() * (containerWidth - btnWidth)
      const randomY = Math.random() * (containerHeight - btnHeight)
      
      noBtn.style.position = 'absolute'
      noBtn.style.left = randomX + 'px'
      noBtn.style.top = randomY + 'px'
    },
    createHearts() {
      for (let i = 0; i < 50; i++) {
        setTimeout(() => {
          const heart = document.createElement('div')
          heart.className = 'hearts'
          heart.textContent = '💕'
          heart.style.left = Math.random() * window.innerWidth + 'px'
          heart.style.top = Math.random() * window.innerHeight + 'px'
          heart.style.fontSize = (Math.random() * 40 + 20) + 'px'
          document.body.appendChild(heart)
          
          setTimeout(() => heart.remove(), 3000)
        }, i * 50)
      }
    }
  }
}
</script>

<style scoped>
</style>
