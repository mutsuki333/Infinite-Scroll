# Infinite-Scroll

A demo [link](https://mutsuki333.github.io/Infinite-Scroll/)

The proper infinite scroll should append new list items by fetching new data.  
But in the demo, with the full list less then 50 items. I Use arrays to store and append new items to the DOM.

The proper way should be like this.

```js
//src/views/Home.vue
append_reps(){
    if(this.end)return
    axios(API).then(res=>{
        if(res.data=='end'){
            this.end = true
            return
        }
        for (let i = 0; i < res.data.length; i++) {
            this.reps_show.push(res.data[i])
        })
    }
}
```
