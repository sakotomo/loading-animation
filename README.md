# loading-animation

> A Vue.js project that has Loading Animation. Although you can use this project alone, I recommend you use it in your project.

## Build Setup (use this project in your project)

1. Copy & Paste Loading.vue file in your project (i.e. under components)
2. Copy & Paste a part of App.vue
```
<Loading :loading="loading"/>

<script>
import Loading from './components/Loading' // <- import Loading.vue

export default {
  data: function (){
    return {
      // If you want to stop loading animation, please change here. loading:false
      loading:true // <- loading variable
    }
  },
  name: 'App',
  components: {
    Loading // <- add component
  }
}
</script>
```


## Build Setup (use this project alone)

install dependencies
```
npm install
```

serve with hot reload at localhost:8080
```
npm run dev
```

build for production with minification
```
npm run build
```


## License
[MIT](http://b4b4r07.mit-license.org)
