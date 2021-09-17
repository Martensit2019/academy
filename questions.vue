<template>
  <div class="questions-page">
    <h4 class="name__block mb_3 questions-page__name-bock">Вопросы и ответы</h4>
    <div class="page questions-page__content">
      <div class="questions-page__left">
        <div class="questions-page__left-slide">
          <div
            class="questions-page__left-slide--title"
            @click="showSlide = !showSlide"
          >
            <div class="questions-page__left-slide--title__right">
              Сортировать вопросы
            </div>
            <div class="questions-page__left-slide--title__left">
              <div class="questions-page__left-slide--title__btns">
                <button class="questions-page__left-slide--title__btn">
                  1
                </button>
                <button class="questions-page__left-slide--title__btn">
                  2
                </button>
                <button class="questions-page__left-slide--title__btn">
                  3
                </button>
              </div>
              <div class="questions-page__left-slide--title__numbers">34 из 245</div>
            </div>
          </div>
          <div class="questions-page__left-slide--body" v-if="showSlide">
            <div class="questions-page__form-wrapper">
              <form action="" class="questions-page__form">
                <select class="questions-page__form-select">
                  <option value="them1">Тема</option>
                  <option value="them2">Тема</option>
                  <option value="them3">Тема</option>
                </select>
                <select>
                  <option value="course1">Курс</option>
                  <option value="course2">Курс</option>
                  <option value="course3">Курс</option>
                </select>
                <select>
                  <option value="course1">Сортировать по</option>
                  <option value="course2">Сортировать по</option>
                  <option value="course3">Курс</option>
                </select>
                <div class="questions-page__form-options">
                  <div class="questions-page__form-options--item">
                    <input
                      id="showAll"
                      type="radio"
                      value="showAll"
                      name="questions"
                      class="questions-page__form-options--input"
                    />
                    <label
                      for="showAll"
                      class="questions-page__form-options--label"
                      ><span>Показать&nbspвсе</span></label
                    >
                  </div>
                  <div class="questions-page__form-options--item">
                    <input
                      id="showMy"
                      checked
                      type="radio"
                      value="showMy"
                      name="questions"
                      class="questions-page__form-options--input"
                    />
                    <label
                      for="showMy"
                      class="questions-page__form-options--label"
                      ><span>Показать&nbspмои</span></label
                    >
                  </div>
                </div>

                <button type="submit" class="btn btn__primary">
                  Задать вопрос
                </button>
              </form>
            </div>
          </div>
        </div>
        <div class="questions-page__left-question--box">
          <div class="questions-page__left-question--question">Вопрос №567</div>
          <div
            class="questions-page__left-question--answer"
            style="height: 200px; border: 1px solid red"
          ></div>
        </div>
      </div>
      <div class="questions-page__right">
        <div class="questions-page__right-content">
          <form action="" class="questions-page__form">
            <div class="questions-page__form-title">Спросить</div>
            <select class="questions-page__form-select">
              <option value="them1">Тема</option>
              <option value="them2">Тема</option>
              <option value="them3">Тема</option>
            </select>
            <select>
              <option value="course1">Курс</option>
              <option value="course2">Курс</option>
              <option value="course3">Курс</option>
            </select>
            <textarea>Напишите свой вопрос</textarea>
            <div class="questions-page__form-file">
              <div class="questions-page__form-file--item">
                <input
                  id="formQuestion"
                  accept=""
                  type="file"
                  class="questions-page__form-file--input"
                />
                <div class="questions-page__form-file--button">
                  Добавить файл к Вашему вопросу
                </div>
              </div>
              <div class="questions-page__form-file--preview"></div>
            </div>

            <button type="submit" class="btn btn__primary">
              Задать вопрос
            </button>
            <a href="#" class="link">Правила сервиса</a>
            <a href="#" class="link">Как правильно задавать вопросы?</a>
          </form>
        </div>
      </div>
    </div>
    <div class="page page-desktop"></div>
    <!-- <div v-if="wishList.length" class="favorite-page__content">
      <template v-for="(item, key) in wishList">
        <program :key="key" :desktop="true" :program="item" />
      </template>
    </div>
    <div v-else class="favorite-page_empty_list">
      <h3>Список избранных программ пуст</h3>
    </div> -->
  </div>
</template>

<script>
import Program from "~/components/programs/layouts/Program";

export default {
  name: "questions",
  components: { Program },
  layout: "educationProgram",
  transition: {
    name: "programs",
    mode: "out-in",
  },
  data() {
    return {
      showSlide: false,
    };
  },
  // methods: {
  //   showSlide(){

  //   }
  // }
  // computed: {
  //   wishList() {
  //     return this.$store.getters["profile/wishList"];
  //   },
  // },
};
</script>

<style></style>
