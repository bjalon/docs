---
title: "API: <nuxt> 컴포넌트"
description: 레이아웃 내부의 페이지 컴포넌트를 보여줍니다.
---

# &lt;nuxt&gt; 컴포넌트

> 이 컴포넌트는 페이지 컴포넌트가 있는 [layouts](/guide/views#layouts)에서만 사용됩니다.

예제 (`layouts/default.vue`):

```html
<template>
  <div>
    <div>My nav bar</div>
    <nuxt/>
    <div>My footer</div>
  </div>
</template>
```

[layouts example](/examples/layouts)에서 예제를 보실 수 있습니다.

**Props**:

- nuxtChildKey: `string`
  - 이 속성은 `<router-view/>`에 `key`속성으로 설정됩니다. 동적 페이지에서 여러 라우트간의 트랜지션을 만드는 경우 유용합니다.
  - 기본값: `$route.path`

`<router-view/>`에 `key`속성을 설정하는 방법은 3가지가 있습니다.

1. `nuxtChildKey` 속성

  ```html
  <template>
     <div>
       <nuxt :nuxt-child-key="someKey"/>
     </div>
  </template>
  ```

2. 각 페이지 컴포넌트의 `key` 옵션: `string` or `function`

  ```js
  export default {
     key(route) {
       return route.fullPath
     }
  }
  ```

3. 각 페이지 컴포넌트의 `watchQuery` 옵션: `boolean` or `string[]`

  [watchQuery](/api/pages-watchquery) 옵션에 설정한 쿼리는 키를 생성할 때 고려됩니다. 만약 `watchQuery`가 `true`라면 `fullPath`를 사용하게 됩니다.

- name: `string` (_introduced with Nuxt v2.4.0_)
  - 이 속성은 `<router-view/>`의 속성으로 설정됩니다. 페이지 컴포넌트의 named-view를 렌더링 하는데 사용됩니다.
  - 기본값: `default`

[named-views example](/examples/named-views)에서 예제를 보실 수 있습니다.
