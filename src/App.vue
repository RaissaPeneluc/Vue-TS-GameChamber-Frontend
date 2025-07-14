<script setup lang="ts">
import { ref } from 'vue'
import { MenuProps } from 'ant-design-vue'

const current = ref<string[]>(['home'])
const itemsNavBar = ref<MenuProps['items']>([
  {
    key: 'home',
    label: 'HOME',
    title: 'HOME',
  },
  {
    key: 'game',
    label: 'GAMEPLAY',
    title: 'GAMEPLAY',
  },
  {
    key: 'live',
    label: 'LIVE',
    title: 'LIVE',
  },
  {
    key: 'sub1',
    label: 'UPCOMING',
    title: 'UPCOMING',
    children: [
      {
        type: 'group',
        label: 'Item 1',
      },
      {
        type: 'group',
        label: 'Item 2',
      },
    ],
  },
  {
    key: 'page',
    label: 'PAGE',
    title: 'PAGE',
  },
])

const itemsCards = ref([
  {
    image: './assets/card1.png',
    title: 'Experienced Trainers',
    description:
      'It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout',
  },
  {
    image: './assets/card2.png',
    title: 'Every Console',
    description:
      'It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout',
  },
  {
    image: './assets/card3.png',
    title: 'Every Console',
    description:
      'It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout',
  },
])
</script>

<template>
  <a-layout>
    <a-layout-header style="background-color: #090909">
      <div class="flex flex-row justify-between pl-10 pr-10 items-center text-white">
        <h1 class="text-2xl">GameChamber</h1>
        <a-menu
          v-model:selectedKeys="current"
          mode="horizontal"
          :items="itemsNavBar"
          style="background-color: #090909; color: white"
        ></a-menu>
        <a-button type="primary">Log In</a-button>
      </div>
    </a-layout-header>

    <a-layout-content class="pl-20 pr-20 bg-[#090909]">
      <section class="grid grid-cols-2 h-screen">
        <div class="w-150 mt-20 text-white">
          <div>
            <h1 class="text-7xl">Find Your Game</h1>
            <h1 class="text-7xl text-blue-500">Tournament</h1>
            <h1 class="text-7xl">Here</h1>
          </div>
          <div class="mt-10">
            <p>
              Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque
              laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi
              architecto beatae vitae dicta sunt explicabo.
            </p>
          </div>
          <a-divider class="bg-gray-600" />
          <a-button class="mt-5">Explore</a-button>
        </div>

        <div class="flex justify-center mt-5">
          <img class="h-200" src="./assets/person.png" />
        </div>
      </section>

      <section class="h-screen">
        <div class="flex justify-center">
          <h1 class="text-white text-4xl">The Best Training for Your Abilities</h1>
        </div>
        <div class="flex justify-center mt-10">
          <a-card
            class="w-70"
            style="margin-left: 20px"
            v-for="(card, index) in itemsCards"
            :key="index"
          >
            <template #cover>
              <img src="./assets/card1.png" />
            </template>
            <a-card-meta
              class="text-center"
              style="margin-top: 5px"
              :title="card.title"
              :bordered="false"
            >
              <template #description>{{ card.description }}</template>
            </a-card-meta>
          </a-card>
        </div>
      </section>
    </a-layout-content>
  </a-layout>
</template>
