<script setup>
import NavPanel from '../components/NavPanel.vue'
import '../assets/resize.css'
</script>

<script>
// import { ref, computed } from 'vue'
// import Column from './Column.vue'
// import Card from './Card.vue'
// import Draggable from 'vuedraggable'

// export default {
//   components: {
//     Column,
//     Card,
//     Draggable
//   },
//   setup() {
//     const columns = ref([
//       { id: 1, title: 'To Do' },
//       { id: 2, title: 'In Progress' },
//       { id: 3, title: 'Done' }
//     ])

//     // Sample cards for each column
//     const sampleCards = [
//       { id: 1, title: 'Task 1', columnId: 1 },
//       { id: 2, title: 'Task 2', columnId: 1 },
//       { id: 3, title: 'Task 3', columnId: 2 },
//       { id: 4, title: 'Task 4', columnId: 2 },
//       { id: 5, title: 'Task 5', columnId: 3 }
//     ]

//     // Initialize cards for each column based on the sampleCards array
//     const initializeCards = () => {
//       columns.value.forEach((column) => {
//         column.cards = sampleCards.filter((card) => card.columnId === column.id)
//       })
//     }

//     // Initialize cards when the component is mounted
//     initializeCards()

//     const acceptDrop = (event, targetColumn) => {
//       event.dataTransfer.dropEffect = 'move'
//       return targetColumn
//     }

//     const handleDrop = (event, targetColumn) => {
//       const draggedCardId = event.dataTransfer.getData('text')
//       const sourceColumn = columns.value.find((column) =>
//         column.cards.some((card) => card.id === parseInt(draggedCardId))
//       )
//       if (!sourceColumn || sourceColumn.id === targetColumn.id) return

//       // Move the dragged card to the target column
//       const index = sourceColumn.cards.findIndex((card) => card.id === parseInt(draggedCardId))
//       sourceColumn.cards.splice(index, 1)
//       targetColumn.cards.push({
//         id: parseInt(draggedCardId),
//         title: 'Task',
//         columnId: targetColumn.id
//       })
//     }

//     const drag = ref({})

//     const endDrag = (result) => {
//       if (!result.item || !result.to) return
//       const draggedId = result.item.element.dataset.cardId
//       const droppedOnColumn = columns.value.find(
//         (column) => column.id === parseInt(result.to.dropzoneId)
//       )

//       // If the card is moved within the same column, do nothing
//       //if (droppedOnColumn.id === dragged.source.columnId) return

//       // const index = droppedOnColumn.cards.findIndex((card) => card.id === parseInt(draggedId))
//       // droppedOnColumn.cards.splice(index, 1)
//       dragged.source.cards.push({
//         id: parseInt(draggedId),
//         title: 'Task',
//         columnId: droppedOnColumn.id
//       })
//     }

//     return {
//       columns,
//       acceptDrop,
//       handleDrop,
//       drag,
//       endDrag
//     }
//   }
// }
</script>

<template>
  <NavPanel />
  <div class="resize">
    <div class="board">
      <Column
        v-for="column in columns"
        :key="column.id"
        :title="column.title"
        @dragover="acceptDrop($event, column)"
        @drop="handleDrop($event, column)"
      >
        <Draggable
          v-model:value="column.cards"
          group="cards"
          @start="drag = { ...$event }"
          @end="endDrag($event)"
        >
          <template #default="{ item }">
            <Card :card="item" />
          </template>
        </Draggable>
      </Column>
    </div>
  </div>
</template>

<style>
/* Extra Small Devices (320px - 479px) */
@media (min-width: 0px) and (max-width: 479px) {
  .about {
    margin-top: 80px;
    margin-left: 15px;
    min-height: 95vh;
    display: flex;
    align-items: center;
  }
}

/* Small Devices (480px - 767px) */
@media (min-width: 480px) and (max-width: 767px) {
  .about {
    margin-left: 0.5em;
    margin-top: 100px;
    min-height: 95vh;
    display: flex;
    align-items: center;
  }
}

/* Medium Devices (768px - 1023px) */
@media (min-width: 768px) and (max-width: 1023px) {
  .about {
    margin-left: 0.5em;
    margin-top: 100px;
    min-height: 95vh;
    display: flex;
    align-items: center;
  }
}

/* Large Devices (1024px - 1279px) */
@media (min-width: 1024px) and (max-width: 1279px) {
  .about {
    margin-left: 3em;
    margin-top: 0;
    min-height: 95vh;
    display: flex;
    align-items: center;
  }
}

/* Extra Large Devices (1280px - 1535px) */
@media (min-width: 1280px) and (max-width: 1535px) {
  .about {
    margin-left: 4.5em;
    margin-top: 0;
    min-height: 95vh;
    display: flex;
    align-items: center;
  }
}

/* Wide Screens (1536px - 1919px) */
@media (min-width: 1536px) and (max-width: 1919px) {
  .about {
    margin-left: 6em;
    margin-top: 0;
    min-height: 95vh;
    display: flex;
    align-items: center;
  }
}

/* Full HD (1920px - 2559px) */
@media (min-width: 1920px) and (max-width: 2559px) {
  .about {
    margin-left: 8em;
    margin-top: 0;
    min-height: 95vh;
    display: flex;
    align-items: center;
  }
}

/* Quad HD (2560px - 3839px) */
@media (min-width: 2560px) and (max-width: 3839px) {
  .about {
    margin-left: 8.5em;
    margin-top: 0;
    min-height: 95vh;
    display: flex;
    align-items: center;
  }
}

/* 4K Screens (3840px and above) */
@media (min-width: 3840px) {
  .about {
    margin-left: 10em;
    margin-top: 0;
    min-height: 95vh;
    display: flex;
    align-items: center;
  }
}
</style>
