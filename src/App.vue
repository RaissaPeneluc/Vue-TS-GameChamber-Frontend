<script setup lang="ts">
import { ref } from 'vue'
import { MenuProps } from 'ant-design-vue'

const current = ref<string[]>(['home'])
const items = ref<MenuProps['items']>([
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
</script>

<template>
  <div>
    <a-page-header class="flex flex-row bg-blue-900" title="GameChamber">
      <div class="flex">
        <a-menu v-model:selectedKeys="current" mode="horizontal" :items="items"></a-menu>
        <a-button type="primary">Log In</a-button>
      </div>
    </a-page-header>

    <main class="bg-amber-950">
      <section class="bg-amber-600 grid grid-cols-2 justify-between">
        <div>
          <h1>Find Your Game Tournament Here</h1>
          <p>
            Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque
            laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi
            architecto beatae vitae dicta sunt explicabo.
          </p>
        </div>
        <div>
          <a-image :width="200" src="./assets/person.png" />
        </div>
      </section>
    </main>
  </div>
</template>
