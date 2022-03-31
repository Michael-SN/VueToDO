<template>
  <div class="line-task px-2">
    <div class="tile">
      <div class="tile-icon">
        <span class="d-flex">
          <i class="icon icon-time centered" />
        </span>
      </div>
      <div class="tile-content">
        <p class="tile-subtitle">{{ todo.description }}</p>
      </div>
      <div class="tile-action">
        <button 
          class="btn btn-link tooltip" 
          @click="$emit('toggle', todo)" 
          data-tooltip="Complete this task"
        >
          <i class="icon icon-check"/>
        </button>
        <button 
          class="btn btn-link tooltip" 
          data-tooltip="Delete this task"
          @click="$emit('remove', todo)"
        >
          <i class="icon icon-delete"/>
        </button>
      </div>
    </div>  
  </div>
</template>

<script>

export default {
  props: {
    todo: {
      type: Object, 
      required: true
    }    
  },
}
</script>

<style scoped>
.line-task {
  transition: all .2s linear;
}
.line-task.checked {
  text-decoration: line-through;
  color: #aeaeae;  
  /* box-shadow: 0 3px 6px #cecefe inset; */
}

.line-task:hover {
  box-shadow: 0 3px 6px #cecefe;
}
.tile {  
  align-items: center;
}

.tile p {
  margin-bottom: 0;
}

.tile i:not(icon-delete) {
  color: #4341d4;
}

.tile i.icon-delete {
  color: red;
}

</style>