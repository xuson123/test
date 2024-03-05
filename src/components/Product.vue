
<template>
  <div class="list">
    <!-- 遍历数据 -->
    <div v-for="user in productData" :key="user.id">
        <p> 商品名称：{{ user.name }}</p>
        <p>商品价格：{{ user.price }}</p>
        <p>平均评分:{{ user.average }}</p>
        <!-- <ul>
            嵌套v-for来读取评分
            <li v-for="reviews in user.reviews" 
            :key="reviews.id" 
            style="margin-left: -40px">
            评分：{{ user.average }}
            </li>
        </ul> -->
    </div>
  </div>
</template>

<script>
// import axios from 'axios'
export default {
//   name: 'Product',
  data(){
    return{
        //定义一个数组去提取res里的data数据
        productData:[],
        users: null,
        res:{    
        "status": "success",
        "data": [
            {
            "average":'',
            "id": 1,
            "name": "Product 1",
            "description": "Description for Product 1",
            "price": 99.99,
            "category": {
                "id": 1,
                "name": "Electronics"
            },
            "images": ["image1.jpg", "image2.jpg"],
            "reviews": [
                {
                "id": 1,
                "rating": 4,
                "comment": "Great product!",         "author": "John Doe"
                },
                // 更多评论...
            ]
            },
            // 更多商品...
        ]
        }
        }
    
    },
    methods:{
        product (){
            this.productData = this.res.data
            // console.log(this.productData.length)
            this.countAver()
        },
        countAver() {
            // let count = 0//分值总数
            let number = 0 //产品个数
            // number = this.prodcutData.length
            for (let i = 0; i < this.productData.length; i++) {
                let count = 0//分值总数
                let arr = this.productData[i].reviews
                this.productData[i].average = ''
                for (let j = 0; j < arr.length; j++) {
                count += arr[j].rating
                }
                this.productData[i].average = count/arr.length
            }
             let average= count/number
        },
        
        
    },
    mounted(){
        this.product()
    }
}
</script>
<style scoped>
 .list ul li {
    list-style: none;
 }
</style>
