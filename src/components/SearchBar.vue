<template>
  <form class="search">
    <input type="text" placeholder="Search" class="search__input" />
    <button class="search__button">
      <search-icon class="navbar__icon--magnifying"></search-icon>
    </button>
  </form>
</template>

<script>
import SearchIcon from "./icons/SearchIcon";
export default {
  components: { SearchIcon
  }
};
</script>

<style lang="scss">
.search {
  flex: 0 0 25%;
  margin: 7px auto;
  align-self: stretch;
  display: flex;

  &__input {
    font-family: inherit;
    border-radius: 6px 0 0 6px;
    min-width: 37rem;
    max-width: 37rem;
    border: none;
    padding-left: 1.5rem;
    margin-right: 0.1rem;

    // font-size: inherit;
    background-color: var(--color-grey-dark-4);
    color: var(--color-grey-light);
    &:hover {
      border: 2px solid var(--color-grey-light-3);
    }

    &:focus {
      outline: none;
      border: 2px solid var(--color-primary);
      background-color: #000;
      color: var(--color-grey-light);
      outline-offset: 0;
    }
    &::-webkit-input-placeholder {
      font-weight: 500;
      color: var(--color-grey-light);
    }
  }
  // &__input:focus + &__button {
  //   background-color: #000;
  // }
  &__button {
    background-color: var(--color-grey-dark-2);
    border-radius: 0 6px 6px 0;
    padding: 0 0.5rem;
    border: none;
  }
}
</style>