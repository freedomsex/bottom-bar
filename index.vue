<script>
export default {
  props: ['centred'],
  data: () => ({}),
};
</script>

<template>
  <div class="bottom-bar">
    <div class="bottom-bar__wrapper" :class="{centred}">
      <slot></slot>
    </div>
  </div>
</template>

<style lang="less">
.bottom-bar {
  position: fixed;
  bottom: 0;
  width: 100%;
  background-color: @white;
  box-shadow: 0 -3px 10px 0 rgba(0, 0, 0, 0.08);
  white-space: nowrap;
  overflow: hidden;
  z-index: 1;

  @min-display: 300px;

  &__wrapper {

    display: flex;
    justify-content: space-between;
    // align-items: center;
    white-space: nowrap;
    overflow: hidden;

    padding: 5px @indent-sm 2px;
    @media (max-width: @min-display) {
      padding: 7px @indent-sm;
    }
    max-width: @document-width;
    margin: 0 auto;

    &.centred {
      justify-content: center;
    }
  }

  .nav-button {
    // flex: 0 auto;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    max-width: 120px;
    white-space: nowrap;
    overflow: hidden;
    padding: 0px 5px;
    position: relative;

    color: @dark-light;
    cursor: pointer;

    &__icon {
      flex: 0 auto;
      font-size: 0px;
      position: relative;

      &-text {
        padding-top: 3px;
        font-size: 20px;
      }
    }

    &__status {
      width: 10px;
      height: 10px;
      position: absolute;
      bottom: 0px;
      right: -3px;
      display: inline-block;
      border-radius: 10px;
      box-shadow: 0 0 0 2px @white;
      vertical-align: middle;
      background-color: @red-dark;
    }

    &__caption {
      flex: 0 auto;
      font-size: 12px;
      @media (max-width: @min-display) {
        display: none;
      }
    }
  }
}
</style>
