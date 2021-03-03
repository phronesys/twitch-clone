<template >
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {

}
</script>

<style>
.btn{
  background-color: var(--color-grey-dark-2);
  border-radius: 5px;
  display: flex;
  align-items: center;
  outline: none;
}

</style>