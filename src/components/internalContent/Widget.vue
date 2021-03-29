<template>
  <div class="page__content__widget">
    <h3 class="page__content__widget__heading">Продуктивність</h3>
    <p class="page__content__widget__description">ЕН / Людину в годину</p>
    <p class="page__content__widget__percentage">
      19,32%<span class="page__content__widget__percentage_info"
        >/ норма 100</span
      >
    </p>
    <p class="page__content__widget__date">пн, 18 березня, 10:56</p>
  </div>
</template>



<style lang="scss" scoped>
  .page__content{
        &__widget{
        height: 200px;
        width: 620px;
        padding: 24px;
        border-radius: 8px;
        background: white;

        &__heading{
            font-weight: bold;
            font-size: 20px;
            line-height: 120%;
            font-family: NovaPoshtaBold, sans-serif;
        }

        &__description{
            color: rgba(32, 33, 36, 0.54);
            font-size: 12px;
            margin-top: 4px;
            line-height: 130%;
        }

        &__percentage{
            font-weight: 900;
            font-size: 48px;
            margin-top: 8px;
            line-height: 130%;
            font-family: NovaPoshtaBlack,sans-serif;
            &_info{
                font-weight: normal;
                font-size: 14px;
                color: rgba(32, 33, 36, 0.6);
                margin-left: 6px;
            }
        }
        &__date{
            font-size: 12px;
            margin-top: 12px;
        }
    }
  }
</style>