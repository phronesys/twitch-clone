<template >
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {};
</script>

<style lang="scss">
.btn {
  text-align: center;
  margin-left: 1rem;
  cursor: pointer;
  border: none;
  outline: none;
  background-color: var(--color-grey-dark-3);
  color: var(--color-grey-light);
  font-weight: 600;
  border-radius: 4px;
  padding: 0.9rem;
  outline: none;
  &:hover {
    background-color: var(--color-grey-dark-4);
  }
  &--primary {
    background-color: var(--color-primary);
    &:hover {
      background-color: var(--color-primary-dark);
    }
  }
  &__login {
    margin: -0.2rem 0.3rem;
  }
}
</style>