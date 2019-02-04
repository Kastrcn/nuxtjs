# nuxtjs demo

> My bee&#39;s knees Nuxt.js project
> 

## router

### nuxt-link

和router-link 用法一样

```vue
<nuxt-link to="/">Home</nuxt-link>
<nuxt-link :to="{name:'post-id', params:{id: item.show.id}}">{{ item.show.name }}</nuxt-link>
```

参考文档 https://zh.nuxtjs.org/guide/routing

## 组件使用

组件使用步骤

1. 导入
2. 声明
3. 使用

```vue
<template>
 <!-- 使用 -->
    <Header/>
</template>
<script>
# 导入
import Header from '~/components/Header.vue'

export default {
    # 声明
  components: {
    Header
  }
}
</script>
```

## layouts使用

和page区别在 添加子渲染标签nuxt

*`<nuxt/> `组件用于显示页面的主体内容。*

```vue
<template>
    <nuxt/>
</template>
```

参考文档 https://zh.nuxtjs.org/guide/views/

## 发送请求并渲染

发送请求并渲染步骤

1. 导入请求对象
2. 发送请求
3. 渲染页面

```vue
<template>
  <div>
    <!-- 渲染页面 -->
   {{data}}
  </div>
</template>
<script>
 # 导入请求对象
import axios from 'axios'
export default {
   # 发送请求
  asyncData() {
    return axios
      .get('https://api.tvmaze.com/search/shows?q=batman')
      .then(res => {
        return { data: res.data }
      })
  },
  methods: {},
  components: {}
}
</script>
```



## Build Setup

``` bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn run dev

# build for production and launch server
$ yarn run build
$ yarn start

# generate static project
$ yarn run generate

# deploy static project 
$ yarn run deploy
```


