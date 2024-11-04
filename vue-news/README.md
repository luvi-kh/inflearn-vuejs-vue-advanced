# vue-news

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### high order component
```
https://legacy.reactjs.org/docs/higher-order-components.html
```

### 네비게이션 가드
```
routes / index.js 

beforeEnter

beforeEnter(routeTo, routeFrom, next) {
        bus.$emit('on:progress');
        const itemId = routeTo.params.id;
        store.dispatch('FETCH_ITEM', itemId)
          .then(() => next())
          .catch(err => new Error('failed to fetch item details', err));
      },
```

### bus.$emit('off:progress'); 위치
### views / CreateListView.js 에서 하면 보다 깔끔함
```
mounted() {
      bus.$emit('off:progress');
    },
```