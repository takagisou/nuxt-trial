<template>
<section>
    <div>
        <span>color</span>
        <span>|</span>
        <span><nuxt-link to="/scheme">scheme</nuxt-link></span>
    </div>

    <div><img :src="data.image.named" /></div>
</section>
</template>

<script>
import axios from 'axios'
export default {
    async asyncData(){
        const hex = Math.floor(Math.random() * 16777215).toString(16)
        const { data } = await axios.get(`https://www.thecolorapi.com/id`,{
            params: {
                // ここにクエリパラメータを指定する
                hex: hex // このようにパラメータを付けるとhttpsになる
            }
        })
        return { data }
    }    
}
</script>

