<script setup>
import NavPanel from '../components/NavPanel.vue'
import '../assets/resize.css'
</script>

<script>
// Test
//
export default {
  data() {
    return {
      isDetailVisible: false
    }
  }
}
</script>

<template>
  <NavPanel />
  <div class="resize">
    <div class="dashboard">
      <a> Test </a>

      <!-- components here -->
      <h1>Welcome to the Dashboard!</h1>
      <p>Here are some examples:</p>

      <button @click="showDetails">Show Details</button>

      <details v-if="isDetailVisible" class="detail-container">
        <summary>Show more details...</summary>
        <!-- more components  can be added here -->
      </details>
    </div>
  </div>
</template>

<!-- <style>
/* Responsivness: */
/* Resize (0px - 479px) */
@media (min-width: 0px) and (max-width: 479px) {
  .dashboard {
    margin-top: 4em;
    margin-left: 15px;
    min-height: 95vh;
    display: block;
    align-items: center;
  }
}

/* Resize (480px - 767px) */
@media (min-width: 480px) and (max-width: 767px) {
  .dashboard {
    margin-left: 0.5em;
    margin-top: 4em;
    min-height: 95vh;
    display: block;
    align-items: center;
  }
}

/* Resize (768px - 1023px) */
@media (min-width: 768px) and (max-width: 1023px) {
  .dashboard {
    margin-left: 0.5em;
    margin-top: 4em;
    min-height: 95vh;
    display: block;
    align-items: center;
  }
}

/* Resize (1024px - 1279px) */
@media (min-width: 1024px) and (max-width: 1279px) {
  .dashboard {
    margin-left: 3em;
    margin-top: 4em;
    min-height: 95vh;
    display: block;
    align-items: center;
  }
}

/* Resize (1280px - 1535px) */
@media (min-width: 1280px) and (max-width: 1535px) {
  .dashboard {
    margin-left: 4.5em;
    margin-top: 4em;
    min-height: 95vh;
    display: block;
    align-items: center;
  }
}

/* Resize (1536px - 1919px) */
@media (min-width: 1536px) and (max-width: 1919px) {
  .dashboard {
    margin-left: 6em;
    margin-top: 4em;
    min-height: 95vh;
    display: block;
    align-items: center;
  }
}

/* Resize (1920px - 2559px) */
@media (min-width: 1920px) and (max-width: 2559px) {
  .dashboard {
    margin-left: 8em;
    margin-top: 4em;
    min-height: 95vh;
    display: block;
    align-items: center;
  }
}

/* Quad HD (2560px - 3839px) */
@media (min-width: 2560px) and (max-width: 3839px) {
  .dashboard {
    margin-left: 8.5em;
    margin-top: 4em;
    min-height: 95vh;
    display: block;
    align-items: center;
  }
}

/* Resize (3840px and above) */
@media (min-width: 3840px) {
  .dashboard {
    margin-left: 10em;
    margin-top: 4em;
    min-height: 95vh;
    display: block;
    align-items: center;
  }
}
</style> -->
