<template>
  <div>
    <div class="education-plan">
      <div
        v-for="(course, key) in program.education_plan"
        :key="key"
        class="education-plan__element"
      >
        <div
          v-b-toggle="'program-' + course.id"
          class="education-plan__header"
          ref="currentEducationPlanHeader"
          @click="isOpen = !isOpen"
        >
          <div class="collapse__icon" :class="{ collapse_icon_open: isOpen }">
            <svg width="10" height="6" viewBox="0 0 10 6">
              <path
                d="M8.76117 0L5 3.61719L1.23883 0L0 1.19141L5 6L10 1.19141L8.76117 0Z"
                fill="#191919"
              />
            </svg>
          </div>
          <NuxtLink
            class="education-plan__title"
            :to="{
              name: 'programs-program_id-course_id',
              params: {
                program_id: program.id,
                course_id: course.id,
              },
            }"
          >
            {{ course.name }}
          </NuxtLink>

          <div class="education-plan__arrow">
            <div class="education-plan__progress mr_4">
              {{ course.success_rate }}%
              <progress-bar
                size="md"
                themes="blue"
                :progress="course.success_rate"
              />
            </div>
          </div>
        </div>
        <b-collapse
          :id="'program-' + course.id"
          class="education-plan__body"
        >
          <div class="course mt_1">
            <div class="course__rating course_rating_excellent">5</div>
            <NuxtLink
              :to="{
                name: 'programs-program_id-course_id-lecture_id',
                params: {
                  program_id: program.id,
                  course_id: course.id,
                  lecture_id: 1,
                },
              }"
              class="course__progress_info"
            >
              <div class="course__name">Управление человечиским капиталом</div>
              <div class="course__duration">11 дней</div>
              <div class="course__percent">100%</div>
            </NuxtLink>
            <progress-bar size="sm" themes="green" :progress="100" />
          </div>
        </b-collapse>
      </div>
    </div>
  </div>
</template>

<script>
import ProgressBar from "~/components/common/ProgressBar";

export default {
  name: "education-plan",
  components: { ProgressBar },
  props: {
    program: {
      type: Object,
      default: null,
    },
  },
  data() {
    return {
      isOpen: false,
    };
  }
};
</script>

<style scoped></style>
