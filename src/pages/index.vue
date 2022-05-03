<script setup lang="ts">
interface GameLink {
  store: string
  url: string
}

const DOMAIN = 'https://game.yuy1n.io/link'

function openPage(url: string) {
  window.open(url, '_blank')
}

const gameLinks: GameLink[] = [
  {
    store: 'Epic',
    url: 'https://store.epicgames.com/zh-CN/p/star-wars-jedi-fallen-order',
  },
  {
    store: 'Steam',
    url: 'https://store.steampowered.com/app/367520/Hollow_Knight/?snr=1_4_4__104_1',
  },
  {
    store: 'Uplay',
    url: 'https://store.ubi.com/cn/game?pid=5ecd2c925cdf9a1528a8c1d1&dwvar_5ecd2c925cdf9a1528a8c1d1_Platform=pcdl&edition=%E6%A0%87%E5%87%86%E7%89%88&source=detail',
  },
  {
    store: 'Xbox',
    url: 'https://www.xbox.com/zh-hk/games/store/-/9P3J32CTXLRZ',
  },
  {
    store: 'PSN',
    url: 'https://www.playstation.com/zh-hant-tw/games/ghost-of-tsushima/',
  },
  {
    store: 'Nintendo',
    url: 'https://store.nintendo.com.hk/70010000019943',
  },
]
</script>

<template>
  <div mb-50px>
    <span text-12>Beautify Game Link</span>
    <span text-4>美化游戏链接</span>
  </div>
  <div mb-50px>
    <span text-6>使用方法：</span>
    <span text-6 text-gray-400>{{ DOMAIN }}?url=</span>
    <span text-6 italic font-bold>&lt;游戏链接></span>
  </div>
  <div v-for="(item,index) in gameLinks" :key="index" flex justify-center mt-4 flex-col items-center gap-3>
    <div text-2xl text-gray-400>
      {{ item.store }}
    </div>
    <img cursor-pointer w-600px :src=" `${DOMAIN}?url=${item.url}`" alt="game" @click="openPage(item.url)">
    <div>
      <span text-gray-400>{{ DOMAIN }}?url=</span>
      <span italic font-bold>{{ item.url }}</span>
    </div>
  </div>
</template>
