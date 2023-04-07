<template>
    <div>
      <h2>Odliczanie do najbliższego meczu {{ targetDate }}</h2>
      <p>{{ days }} dni, {{ hours }} godzin, {{ minutes }} minut, {{ seconds }} sekund</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Timer',
    props: {
        targetDate: {
            type: String,
            default: () => 'Pusty string'
        }
    },
    data() {
        return {
            
        }
    },
  
    created() {
      this.startTimer()
    },
  
    beforeDestroy() {
      clearInterval(this.timerId)
    },
  
    methods: {
      startTimer() {
        this.updateTime()
        this.timerId = setInterval(this.updateTime, 1000)
      },
  
      updateTime() {
        const targetTime = new Date(this.targetDate).getTime()
        const now = new Date().getTime()
        const difference = targetTime - now
  
        if (difference < 0) {
          clearInterval(this.timerId)
          return
        }
  
        const oneDay = 1000 * 60 * 60 * 24
        const oneHour = 1000 * 60 * 60
        const oneMinute = 1000 * 60
        const oneSecond = 1000
  
        this.days = Math.floor(difference / oneDay)
        this.hours = Math.floor((difference % oneDay) / oneHour)
        this.minutes = Math.floor((difference % oneHour) / oneMinute)
        this.seconds = Math.floor((difference % oneMinute) / oneSecond)
      },
    },
  }
  </script>