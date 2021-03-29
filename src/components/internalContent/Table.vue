<template>
    <table class="page__content__table">
        <tr class="page__content__table__row">
          <th class="page__content__table__row__head">Показник</th>
          <th class="page__content__table__row__head">План</th>
          <th class="page__content__table__row__head">Факт (Значення)</th>
          <th class="page__content__table__row__head">Виконання в %</th>
          <th class="page__content__table__row__head">Прогноз</th>
          <th class="page__content__table__row__head">Прогноз в %</th>
          <th class="page__content__table__row__head">Факт (Актуальність)</th>
        </tr>
        <tr class="page__content__table__row">
          <td class="page__content__table__row__item">
            Вантажообіг, ЕН (НП + Пф)
          </td>
          <td class="page__content__table__row__item">{{row_1.plan}}</td>
          <td class="page__content__table__row__item page__content__table__row__item_danger">{{row_1.value}}</td>
          <td class="page__content__table__row__item" :class="row_1.triggerColor">{{calculateMethod1(row_1.value,row_1.plan,row_1)}}%</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">Сьогодні, 12:00</td>
        </tr>
        <tr class="page__content__table__row">
          <td class="page__content__table__row__item">Черга, оцінка</td>
          <td class="page__content__table__row__item">{{row_2.plan}}</td>
          <td
            class="page__content__table__row__item page__content__table__row__item_success"
          >
            {{row_2.value}}
          </td>
          <td class="page__content__table__row__item" :class="row_2.triggerColor">{{calculateMethod1(row_2.value,row_2.plan,row_2)}}%</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">Вчора, 12:00</td>
        </tr>
        <tr class="page__content__table__row">
          <td class="page__content__table__row__item">
            Стандарт швидкості, шт / млн. ШК
          </td>
          <td class="page__content__table__row__item">{{row_3.plan}}</td>
          <td
            class="page__content__table__row__item page__content__table__row__item_success"
          >
            {{row_3.value}}
          </td>
          <td class="page__content__table__row__item" :class="row_3.triggerColor">{{calculateMethod1(row_3.value,row_3.plan,row_3)}}%</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">Вчора, 12:00</td>
        </tr>
        <tr class="page__content__table__row">
          <td class="page__content__table__row__item">
            Продуктивність, ЕН / люд. год
          </td>
          <td class="page__content__table__row__item">{{row_4.plan}}</td>
          <td
            class="page__content__table__row__item page__content__table__row__item_danger"
          >
            {{row_4.value}}
          </td>
          <td class="page__content__table__row__item" :class="row_4.triggerColor">{{calculateMethod2(row_4.value,row_4.plan,row_4)}}%</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">Вчора, 12:00</td>
        </tr>
        <tr class="page__content__table__row">
          <td class="page__content__table__row__item">
            Продуктивність Візит / люд. год
          </td>
          <td class="page__content__table__row__item">{{row_5.plan}}</td>
          <td
            class="page__content__table__row__item page__content__table__row__item_danger"
          >
            {{row_5.value}}
          </td>
          <td class="page__content__table__row__item" :class="row_5.triggerColor">{{calculateMethod2(row_5.value,row_5.plan,row_5)}}%</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">16 березня, 10:56</td>
        </tr>
        <tr class="page__content__table__row">
          <td class="page__content__table__row__item">
            % Інтернет документів
          </td>
          <td class="page__content__table__row__item">{{row_6.plan}}%</td>
          <td
            class="page__content__table__row__item page__content__table__row__item_danger"
          >
            {{row_6.value}}%
          </td>
          <td class="page__content__table__row__item" :class="row_6.triggerColor">{{calculateMethod2(row_6.value,row_6.plan,row_6)}}%</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">16 березня, 10:56</td>
        </tr>
        <tr class="page__content__table__row">
          <td class="page__content__table__row__item">
            % Ідентифікації карткою
          </td>
          <td class="page__content__table__row__item">{{row_7.plan}}%</td>
          <td
            class="page__content__table__row__item page__content__table__row__item_danger"
          >
            {{row_7.value}}%
          </td>
          <td class="page__content__table__row__item" :class="row_7.triggerColor">{{calculateMethod2(row_7.value,row_7.plan,row_7)}}%</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">16 березня, 10:56</td>
        </tr>
        <tr class="page__content__table__row">
          <td class="page__content__table__row__item">
            % ЕН опрацьованих через МД
          </td>
          <td class="page__content__table__row__item">{{row_8.plan}}%</td>
          <td
            class="page__content__table__row__item page__content__table__row__item_danger"
          >
            {{row_8.value}}%
          </td>
          <td class="page__content__table__row__item" :class="row_8.triggerColor">{{calculateMethod2(row_8.value,row_8.plan,row_8)}}%</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">Сьогодні, 12:00</td>
        </tr>
        <tr class="page__content__table__row">
          <td class="page__content__table__row__item">
            % ЕН опрацьованих через РМС
          </td>
          <td class="page__content__table__row__item">{{row_9.plan}}%</td>
          <td
            class="page__content__table__row__item page__content__table__row__item_danger"
          >
            {{row_9.value}}%
          </td>
          <td class="page__content__table__row__item" :class="row_9.triggerColor">{{calculateMethod2(row_9.value,row_9.plan,row_9)}}%</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">-</td>
          <td class="page__content__table__row__item">Вчора, 12:00</td>
        </tr>
        <tr class="page__content__table__row">
          <td class="page__content__table__row__item">
            Вантажообіг, ЕН (НП + Пф)
          </td>
          <td class="page__content__table__row__item">{{row_10.plan}}</td>
          <td
            class="page__content__table__row__item page__content__table__row__item_danger"
          >
            {{row_10.value}}
          </td>
          <td class="page__content__table__row__item" :class="row_10.triggerColor">{{calculateMethod2(row_10.value,row_10.plan,row_10)}}%</td>
          <td
            class="page__content__table__row__item  page__content__table__row__item_danger"
          >
            2329
          </td>
          <td class="page__content__table__row__item">11%</td>
          <td class="page__content__table__row__item">Вчора, 12:00</td>
        </tr>
        <tr class="page__content__table__row">
          <td class="page__content__table__row__item">Людино-години</td>
          <td class="page__content__table__row__item">{{row_11.plan}}</td>
          <td
            class="page__content__table__row__item page__content__table__row__item_success"
          >
            {{row_11.value}}
          </td>
          <td class="page__content__table__row__item" :class="row_11.triggerColor">{{calculateMethod1(row_11.value,row_11.plan,row_11)}}%</td>
          <td
            class="page__content__table__row__item page__content__table__row__item_success"
          >
            15%
          </td>
          <td class="page__content__table__row__item">15%</td>
          <td class="page__content__table__row__item">Сьогодні, 12:00</td>
        </tr>
        <tr class="page__content__table__row"></tr>
      </table>
</template>


<script>
export default {
  data(){
    return {
      row_1: { plan: 50, value: 50, triggerColor: '' },
      row_2: { plan: 2.0, value: 0.0, triggerColor: '' },
      row_3: { plan: 5000, value: 0, triggerColor: '' },
      row_4: { plan: 19.32, value: 14.98, triggerColor: '' },
      row_5: { plan: 20, value: 8.73, triggerColor: '' },
      row_6: { plan: 70, value: 40.4, triggerColor: '' },
      row_7: { plan: 40, value: 33.9, triggerColor: '' },
      row_8: { plan: 20, value: 4.4, triggerColor: '' },
      row_9: { plan: 35, value: 33.1, triggerColor: '' },
      row_10: { plan: 20441, value: 2329, triggerColor: '' },
      row_11: { plan: 1058, value: 156, triggerColor: '' }
    }
  },
  methods:{
    calculateMethod1(par1,par2,row){
      const result = Math.floor((par1/par2)*100);
      if(result>=100){
        row.triggerColor = 'red';
      }else if(result<100){
        row.triggerColor = 'green';
      }
      return result;
    },
    calculateMethod2(par1,par2,row){
      const result = Math.floor((par1/par2)*100);
      if(result>=100){
        row.triggerColor = 'green';
      }else if(result<100 && result>=90 ){
        row.triggerColor = 'orange';
      }else if(result<90){
         row.triggerColor = 'red';
      }
      return result;
    }
  }
}
</script>

<style lang="scss" scoped>
  .page__content{
    &__table{
        border-collapse: collapse;
        background: #F6F6F6;
        width: 100%;
        border-radius: 8px;
        margin-top: 16px;

        &__row{
            height: 56px;
            border-bottom: 2px solid #E0E0E0;

            &:nth-child(1){
                height: 40px;
            }

            &:nth-last-child(-n+1){
                border-bottom: none;
                height: 40px;
            }

            &__item{
                font-size: 14px;
                line-height: 110%;
                text-align: right;
                min-width: 114px;

                &_success{
                    color: #2EBA77;
                }

                &_danger{
                    color: #DA291C;
                }

                &:nth-child(1){
                    text-align: left;
                    padding-left: 24px;
                }
                &:nth-last-child(-n+1){
                    padding: 0 24px 0 50px;
                }
            }

            &__item.red{
              color: #DA291C;
            }
            &__item.orange{
              color: orange;
            }
            &__item.green{
              color: #2EBA77;
            }
            
            &__head{
                font-size: 12px;
                line-height: 110%;
                text-align: right;
                color: rgba(32, 33, 36, 0.6);

                &:nth-child(1){
                    text-align: left;
                    padding-left: 24px;
                }
                &:nth-last-child(-n+1){
                    padding-right: 24px;
                }
            }
        }
    }
  }
</style>