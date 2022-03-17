<template>
  <div class="tile">
    <div class="tile-icon">
      <span class="d-flex">
        <i class="icon icon-time centered" />
      </span>
    </div>
    <div class="tile-content">
      <p class="tile-subtitle">{{ todo.descripion }}</p>
    </div>
    <div class="tile-action">
      <button class="btn btn-link">
        <i class="icon icon-check"/>
      </button>
      <button class="btn btn-link">
        <i class="icon icon-delete"/>
      </button>
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
  } 
}
</script>
