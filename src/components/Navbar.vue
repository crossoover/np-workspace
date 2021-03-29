<template>
  <div class="page__navbar">
    <div class="page__navbar__left">
      <img
        class="page__navbar__left__logo"
        src="../assets/Logo.png"
        alt="Logo"
      />
      <a href="#" class="page__navbar__left__text">Робочий простір</a>
    </div>
    <div class="page__navbar__right">
      <img
        class="page__navbar__right__options"
        src="../assets/Menu.png"
        alt="options"
      />
      <img class="page__navbar__right__user" src="../assets/User.png" alt="" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.page__navbar{
    position: fixed;
    background: white;
    width: 100vw;
    height: 64px;
    padding: 0 28px;
    display: flex; 
    align-items: center;
    justify-content: space-between;

    &__left{
        display: flex;
        align-items: center;

        &__logo{
            width: 32px;
            height: 32px;
        }
        
        &__text{
            margin-left: 12px;
            text-decoration: none;
        }
    }

    &__right{
        display: flex;
        align-items: center;

        &__options{
            width: 16px;
            height: 16px;
            margin-right: 20px;
            cursor: pointer;
        }

        &__user{
            width: 32px;
            height: 32px;
            cursor: pointer;
        }
    }
}
</style>