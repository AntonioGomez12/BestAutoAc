<template>
    <div class="image-viewer">
      <!-- Image container with navigation buttons -->
     
        <!-- Navigation buttons -->
        <v-btn
          variant="icon"
          :disabled="currentIndex === 0"
          @click="prev"
          class="nav-button left"
        >
          <span class="mdi mdi-chevron-left"></span>
        </v-btn>
        <v-btn
          variant="icon"
          :disabled="currentIndex === images.length - 1"
          @click="next"
          class="nav-button right"
        >
          <span class="mdi mdi-chevron-right"></span>
        </v-btn>
  
        <!-- Image -->
        <img :src="currentImage" alt="Image" class="image" />
  
        <!-- Indicators (small circles) -->
        <v-card-actions class="indicators-container">
          <v-btn
            v-for="n in images.length"
            :key="`indicator-${n}`"
            :variant="currentIndex === n - 1 ? 'text' : 'outlined'"
            icon
            @click="goToImage(n - 1)"
            class="indicator"
          >
            <span class="mdi mdi-record"></span>
          </v-btn>
        </v-card-actions>
     
    </div>
  </template>
  
  <script>
  // Import your images or use the appropriate paths
  import ac1 from "@/assets/ac1.jpg";
  import ac2 from "@/assets/ac2.jpg";
  import ac3 from "@/assets/ac3.jpg";
  
  export default {
    name: "ImageViewer",
    data() {
      return {
        images: [ac1, ac2, ac3], // Replace with your imported images or image paths
        currentIndex: 0,
        autoSwitchInterval: null,
      };
    },
    computed: {
      currentImage() {
        return this.images[this.currentIndex];
      },
      activeIndicator() {
        return this.currentIndex + 1;
      },
    },
    methods: {
      prev() {
        this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
      },
      next() {
        this.currentIndex = (this.currentIndex + 1) % this.images.length;
      },
      goToImage(index) {
        this.currentIndex = index;
      },
      startAutoSwitch() {
        this.autoSwitchInterval = setInterval(() => {
          this.next();
        }, 10000); // 10 seconds interval
      },
      stopAutoSwitch() {
        clearInterval(this.autoSwitchInterval);
      },
    },
    mounted() {
      // Start auto-switching on component mount
      this.startAutoSwitch();
    },
    beforeDestroy() {
      // Stop auto-switching on component destroy
      this.stopAutoSwitch();
    },
  };
  </script>
  
  <style>
  /* Add your CSS styles for the image viewer here */
  .image-viewer {
    display: flex;
    position: relative;
    top: 0;
    left: 0;
    justify-content: center;
    align-items: center;
    height: 75vh;
    width: 100%;
  }
  

  .image {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  
  .nav-button {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    color: #fff;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 1;
  }
  
  .nav-button.left {
    left: 0;
  }
  
  .nav-button.right {
    right: 0;
  }
  
  .indicators-container {
    position: absolute;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
  }
  
  .indicator {
    margin: 0 5px;
  }
  
  .v-btn--outlined:not(.v-btn--disabled) .mdi {
    color: #fff;
  }
  
  .v-btn--text:not(.v-btn--disabled) .mdi {
    color: #000;
  }
  </style>
  