<template>
  <div class="flex justify-center">
    <div class="w-64">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Name</th>
          </tr>
        </thead>
        <draggable v-model="list" tag="tbody" handle=".handle">
          <tr v-for="element in list" :key="element.id">
            <td>{{ element.id }}</td>
            <td>{{ element.name }}</td>
          </tr>
        </draggable>
      </table>
    </div>
    <rawDisplays class="w-64" :value="list" />
  </div>
</template>

<script>
import { VueDraggableNext } from '/@'
import rawDisplays from './rawDisplay.vue'

export default {
  components: {
    draggable: VueDraggableNext,
    rawDisplays,
  },
  data() {
    return {
      list: [
        { name: 'John', id: 1 },
        { name: 'Joao', id: 2 },
        { name: 'Jean', id: 3 },
        { name: 'Gerard', id: 4 },
      ]
    }
  },
  methods: {
    log(event) {
      console.log(event)
    }
  }
}
</script>
