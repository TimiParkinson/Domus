<script lang="ts">
    let slides: number = 4;
    let currentSlide: number = 0;
    let slideType: 'single' | 'double' = 'single'; // Determines which type of slide to show
  
    // Function to move to the next slide
    function nextSlide() {
      currentSlide = (currentSlide + 1) % slides;
    }
  
    // Function to move to the previous slide
    function prevSlide() {
      currentSlide = (currentSlide - 1 + slides) % slides;
    }
  
    // Function to set a specific slide (for dot navigation)
    function goToSlide(index: number) {
      currentSlide = index;
    }
  
    // Function to toggle slide type
    function toggleType(type: 'single' | 'double') {
      slideType = type;
      currentSlide = 0; // Reset to the first slide when toggling
    }
  </script>
  
  <style lang="scss">
    #slideshow {
      position: relative;
      overflow: hidden;
      width: 100%;
      max-width: 800px;
      margin: 2rem auto;
      height: 250px;
  
      .slides-container {
        display: flex;
        transition: transform 0.5s ease-in-out;
        transform: translateX(calc(-100% * var(--current-slide, 0)));
        width: 100%;
      }
  
      .slide {
        flex: 0 0 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 2rem;
        background-color: #1e1e1e;
        border-radius: 12px;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
  
        .content {
          display: flex;
          justify-content: center;
          align-items: center;
          height: 200px;
          width: 100%;
          background-color: #333;
          border-radius: 8px;
          color: #b0b0b0;
          font-size: 1rem;
          text-align: center;
          border: 1px solid #444;
  
          &:hover {
            background-color: #4CAF50;
            color: #ffffff;
            transform: scale(1.05);
            transition: all 0.3s ease;
          }
        }
      }
  
      .controls {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        display: flex;
        justify-content: space-between;
        width: 100%;
        pointer-events: none;
  
        .button {
          pointer-events: auto;
          background-color: rgba(0, 0, 0, 0.5);
          color: white;
          border: none;
          border-radius: 50%;
          width: 40px;
          height: 40px;
          display: flex;
          justify-content: center;
          align-items: center;
          cursor: pointer;
          font-size: 1.5rem;
          transition: background-color 0.3s ease;
  
          &:hover {
            background-color: #4CAF50;
          }
        }
      }
    }
  
    #slider {
      display: flex;
      justify-content: center;
      gap: 0.5rem;
      margin: 1rem 0;
  
      .point {
        width: 12px;
        height: 12px;
        background-color: #b0b0b0;
        border-radius: 50%;
        cursor: pointer;
        transition: background-color 0.3s ease, transform 0.3s ease;
  
        &.active {
          background-color: #4CAF50;
          transform: scale(1.3);
        }
  
        &:hover {
          background-color: #4CAF50;
        }
      }
    }
  
    #type {
      display: flex;
      justify-content: center;
      gap: 2rem;
  
      p {
        font-size: 1.2rem;
        font-weight: bold;
        color: #b0b0b0;
        padding: 0.5rem 1rem;
        border: 1px solid #444;
        border-radius: 8px;
        cursor: pointer;
        transition: background-color 0.3s ease, color 0.3s ease;
  
        &.active {
          background-color: #4CAF50;
          color: #ffffff;
        }
  
        &:hover {
          background-color: #4CAF50;
          color: #ffffff;
        }
      }
    }
  </style>

  
  <div id="slideshow">
    <div
      class="slides-container"
      style="--current-slide: {currentSlide};"
    >
      {#each { length: slides } as _, i}
        <div class="slide">
          {#if slideType === 'single'}
            <div class="content">[picture of a single]</div>
          {:else}
            <div class="content">[picture of a double]</div>
          {/if}
        </div>
      {/each}
    </div>
  
    <div class="controls">
      <button class="button" on:click={prevSlide}>&lt;</button>
      <button class="button" on:click={nextSlide}>&gt;</button>
    </div>
  </div>
  
  <div id="slider">
    {#each { length: slides } as _, i}
      <div
        class="point {currentSlide === i ? 'active' : ''}"
        on:click={() => goToSlide(i)}
      ></div>
    {/each}
  </div>

  <div id="type">
    <p
      class:active={slideType === 'single'}
      on:click={() => toggleType('single')}
    >
      I
    </p>
    <p
      class:active={slideType === 'double'}
      on:click={() => toggleType('double')}
    >
      II
    </p>
  </div>
  