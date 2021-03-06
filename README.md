# Nuxt moduleとは？

# computed

例えば vueが持つデータ index が 奇数ならred、偶数ならばbleuとHTMLのクラスを付けたい場合を想定
HTML側で cumputed に定義した奇数か偶数か判断するメソッドを呼ぶような場面で使う
同様の事は methods でも可能だが methodsは都度実行されるが computed はindexが変わらない限り実行されず同じ結果を返す。

# mutationとは？

$storeを書き換えるにはmutationを経由するルール
コンポーネント側で$store.commit()するとvuexのmutationに送られる
mutationは必ず同期。ajaxなど非同期通信をしたいならば**action**を使う。
mutationからaction内のメソッドを呼び出す。


# what's does it mean ?

子をクリックすると'childEvent'が起きたことを親に伝える<br>
'childEvent'が起きた知らせを受けると親は'parentMethod'を実行する<br>
<br>
[Vue.jsで$emitとv-onを使った子から親のコンポーネントにおける値の受け渡し](https://designsupply-web.com/knowledgeside/5599/)

```
// 親
<template>
  <Child @childEvent="parentMethod" />
  <Child2 @toggle="parentToggle" /> // 子２で'toggle'発火
</template>

// 子
<template>
  <div @click="$emit('childEvent')"> // 子要素（自身も？）でのclickを検知し'childEvent'を発火
    <button>子</button>
  </div>
</template>

// 子2
<template>
  <div @click="$emit('toggle')">
  子
  </div>
</template>
```




# my-first-nuxt-app

> My transcendent Nuxt.js project

## Build Setup

```bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).
