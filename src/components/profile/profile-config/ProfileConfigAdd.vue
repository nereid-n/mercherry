<template>
  <div class="row">
    <div class="col">
      <h3 class="mb-2 fs-22 font-weight-normal">Дополнительная информация</h3>
      <form>
        <div class="alert alert-warning mb-2">
          Выбирайте какие вакансии вас интересуют и мы будем информировать вас о новых вакансиях.
        </div>
        <div class="form-group mb-2">
          <h3 class="mb-2 fs-22 font-weight-normal">Интересующий тип вакансии</h3>
          <div>
            <label class="checkbox mr-2">
              <input type="checkbox">
              <span class="checkbox__circle"></span>
              <span>Полная занятость</span>
            </label>
            <label class="checkbox mr-2">
              <input type="checkbox">
              <span class="checkbox__circle"></span>
              <span>Частичная занятость</span>
            </label>
            <label class="checkbox">
              <input type="checkbox">
              <span class="checkbox__circle"></span>
              <span>Разовые задания</span>
            </label>
          </div>
        </div>
        <div class="form-group">
          <label class="checkbox">
            <input type="checkbox">
            <span class="checkbox__circle"></span>
            <span>Получать подходящие вам вакансии на почту</span>
          </label>
        </div>
        <div class="alert alert-warning">
          Заполните данные по городу, метро или районам по которым мы будем предлагать вам вакансии.
          Вы можете указать несколько станций метро/районов
        </div>
        <div class="form-group">
          <label class="control-label" for="advancedprofileform-city">Город</label>
          <div class="position-relative">
            <input type="text"
                   id="advancedprofileform-city"
                   class="form-control"
                   name="city"
                   v-validate="'required'"
                   v-model="modelCity"
                   autocomplete="off"
                   ref="city"
                   @focus="city.focused = true"
                   @blur="focusFalse('city')"
                   @input="dropdownRequest({name: 'city', obj: {q: modelCity}})"
            >

            <ul class="dropdown-input" v-if="profileCity.length > 0 && city.focused && city.dropdownValue.length > 0">
              <li v-for="(dropdownItem, index) in city.dropdownValue"
                  ref="cityDrop"
                  @click="choiceValue('city', index)"
              >
                {{dropdownItem}}
              </li>
            </ul>
          </div>
        </div>

        <div class="form-group mb-4">
          <label class="control-label" for="dt-add">Район</label>
          <div class="position-relative">
            <input type="text"
                   id="dt-add"
                   class="form-control"
                   name="district"
                   v-model="district.name"
                   autocomplete="off"
                   @focus="district.focused = true"
                   @blur="focusFalse('district')"
                   @input="dropdownRequest({name: 'district', obj: {q: district.name, city: modelCity}})"
            >

            <ul class="dropdown-input" v-if="district.name.length > 0 && district.focused && district.dropdownValue.length > 0">
              <li v-for="(dropdownItem, index) in district.dropdownValue"
                  @click="choiceValue('district', index)"
                  ref="districtDrop"
              >
                {{dropdownItem}}
              </li>
            </ul>
          </div>
        </div>
        <div class="alert alert-warning mb-2">
          Указывайте магазины в которых вы уже работаете. Мы покажем ваш отклик работодателю в числе
          первых по вакансиям в магазинах где вы уже работаете.
        </div>
        <div class="form-group mb-3">
          <label class="control-label" for="n-add">Сеть</label>
          <input data-toggle="modal" :data-target="cityFlags.invalid ? '#cityModal' : ''" type="text" id="n-add" class="form-control" placeholder="Укажите адрес сети">
        </div>
        <div>
          <div class="row">
            <div class="col"></div>
          </div>
        </div>
        <div class="form-row mt-3 mb-2 align-items-center">
          <div class="col-3">
            <button type="submit" class="btn btn-secondary">Сохранить</button>
          </div>
        </div>
        <div class="alert alert-warning">
          <p>Вы можете приглашать своих друзей на платформу, отправляя им эту ссылку. Если человек за полгода
            устроиться на любую вакансию ( не задание) с сайта, то вы получаете 1000 рублей, а он за выход на
            работу и отработку 3 дней получает 500 рублей.</p>
          <strong>Реферальная ссылка:</strong> {{dataUser.invite_url}}
        </div>
      </form>
    </div>
  </div>
</template>

<script>
  import { mapFields } from 'vee-validate';
  import cityMixin from '../../../mixins/cityMixin'
  import {mapGetters, mapActions} from 'vuex';

  export default {
    name: "ProfileConfigAdd",
    data() {
      return {
        district: {
          focused: false,
          name: '',
          dropdownValue: []
        },
      }
    },
    methods: {
      validateBeforeSubmit() {
        this.$validator.validateAll().then((result) => {
          if (result) {
            // eslint-disable-next-line
            alert('Form Submitted!');
            return;
          }

          alert('Correct them errors!');
        });
      },
      ...mapActions({
        DISTRICT_LIST: 'lists/DISTRICT_LIST'
      }),
    },
    computed: {
      ...mapFields({
        cityFlags: 'city'
      }),
      ...mapGetters({
        dataUser: 'profile/dataUser'
      }),
    },
    mixins: [cityMixin],
  }
</script>

<style lang="scss">
  .dropdown-input {
    position: absolute;
    z-index: 10;
    top: calc(100% + 2px);
    left: 0;
    width: 100%;
    padding: 10px 0;
    background-color: #fff;
    border: 1px solid rgba(0,0,0,.15);
    border-radius: 2em;
    box-shadow: 0 6px 12px rgba(0,0,0,.175);
    overflow: hidden;
    li {
      display: block;
      padding: 3px 20px;
      clear: both;
      font-weight: 400;
      line-height: 1.4;
      font-size: 14px;
      color: #333;
      white-space: nowrap;
      cursor: pointer;
      &:hover {
        background-color: #f5f5f5;
      }
    }
  }
</style>