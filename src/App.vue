<template>
  <q-layout view="lHh Lpr lFf">
    <q-header
        elevated
        class="bg-secondary"
    >
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
          icon="menu"
        />

        <q-toolbar-title>
          Test App
        </q-toolbar-title>

      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      dark
    >
      <q-list>
        <q-item-label header>Страницы</q-item-label>
        <q-item active-class="text-positive" clickable to="/">
          <q-item-section avatar>
            <q-icon name="school" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Главная</q-item-label>
            <q-item-label class="text-white" caption>Обо мне</q-item-label>
          </q-item-section>
        </q-item>

        <q-item active-class="text-positive" clickable to="about">
          <q-item-section avatar>
            <q-icon name="code" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Задание</q-item-label>
            <q-item-label class="text-white" caption>Которое необязательное</q-item-label>
          </q-item-section>
        </q-item>

        <q-item active-class="text-positive" clickable tag="a" href="https://github.com/mrclll84/yandex" target="_blank">
          <q-item-section avatar>
            <q-icon name="summarize" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Github</q-item-label>
            <q-item-label class="text-white" caption>Гит проекта</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view/>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'

const leftDrawerOpen = ref(false)
</script>
