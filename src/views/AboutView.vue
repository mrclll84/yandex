<template>
  <div class="about bg-dark text-white q-px-xl">


    <h1 class="text-h6 text-center q-mt-none q-pt-md">Задание: Создание интерактивного калькулятора</h1>

    <p class="text-bolder subtitle">
      Описание:

      <p class="p_default">
        Предлагается создать интерактивный калькулятор с использованием Vue.js. Калькулятор должен выполнять основные арифметические операции (сложение, вычитание, умножение и деление). Это задание поможет подросткам изучить основы Vue.js и как они могут использовать JavaScript для создания интерактивных веб-приложений.
      </p>
    </p>


    <q-stepper
        v-model="step"
        vertical
        class="bg-dark q-mb-xl"
        color="primary"
        animated
    >
      <q-step
          :name="1"
          title="Новый проект"
          icon="settings"
          done-color="positive"
          :done="step > 1"
      >
        Создайте новый проект Vue.js или используйте существующий.

        <q-stepper-navigation>
          <q-btn @click="step = 2" color="primary" label="Выполнено" />
        </q-stepper-navigation>
      </q-step>

      <q-step
          :name="2"
          title="Разработка"
          icon="create_new_folder"
          done-color="positive"
          :done="step > 2"
      >
        Создайте компонент калькулятора, который будет содержать поле для ввода чисел, кнопки для операций и поле для вывода результата.
        Используйте связывание данных (v-model) для связи поля ввода с данными в компоненте.
        Создайте методы в компоненте для выполнения операций (сложение, вычитание, умножение, деление) на введенных числах и вывода результата.
        Свяжите кнопки операций с соответствующими методами.
        Добавьте стили для калькулятора, чтобы он выглядел привлекательно.

        <q-stepper-navigation>
          <q-btn @click="step = 3" color="primary" label="Выполнено" />
          <q-btn flat @click="step = 1" color="primary" label="Назад" class="q-ml-sm" />
        </q-stepper-navigation>
      </q-step>

      <q-step
          :name="3"
          title="Дополнительные задания"
          icon="assignment"
          done-color="positive"
          :done="step > 3"
      >
        Добавьте возможность очистки поля ввода и результата.
        Реализуйте обработку ошибок (например, если пользователь пытается поделить на ноль).
        Добавьте анимацию или переходы между операциями для более интересного визуального эффекта.
        <q-stepper-navigation>
          <q-btn @click="step = 4" color="primary" label="Выполнено" />
          <q-btn flat @click="step = 2" color="primary" label="Назад" class="q-ml-sm" />
        </q-stepper-navigation>
      </q-step>

      <q-step
          :name="4"
          title="Проверка"
          icon="add_comment"
      >
        Выложи задание в гитхаб и нажми кнопку отправить
        <q-stepper-navigation>
          <q-btn color="primary" label="Отправить мне" />
          <q-btn flat @click="step = 3" color="primary" label="Назад" class="q-ml-sm" />
        </q-stepper-navigation>
      </q-step>
    </q-stepper>


    <h2 class="text-h6 text-center q-mt-none q-pt-md"> Это задание поможет подросткам понять, как работает двустороннее связывание данных в Vue.js и как они могут создавать интерактивные приложения, используя JavaScript. Кроме того, они смогут улучшить свои навыки в стилизации с помощью CSS.</h2>

  </div>
</template>

<script setup>
import { ref } from 'vue';

const step = ref(1)
</script>

<style lang="scss">
$headerHeight: 50px;
.about{
  height: calc(100vh - #{$headerHeight});

  .subtitle{
    font-size: 18px;
  }

  .p_default{
    font-size: 16px;
  }

  .q-stepper{
    border: 1px solid white;
  }

  .q-stepper__dot:before,
  .q-stepper__dot:after{
    background-color: rgba(255,255,255, .5);
  }
}
</style>
