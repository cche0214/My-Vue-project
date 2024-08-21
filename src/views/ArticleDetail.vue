<template>
  <div>
    <WebHead></WebHead>

    <WebNavigation></WebNavigation>

    <div class="body">
      <div class="container">
        
        <div class="content" v-if="Number(DetailTemple)">

          <h1 class="heading">{{cardListStory[DetailId-1].title}}</h1>
          <hr class="heading-hr">
          <p class="info">发布者：E新向党实践团 发布时间：2024-7-28</p>
          <!-- <video src="../assets/videos/video-01.mp4" autoplay controls :width="640" :height="360"></video> -->
          <img class="textimg" src="../assets/images/CUMT-view1.jpg" alt="笑脸">
          <span class="textexp">笑脸</span>
          <p class="text">
            {{cardListStory[DetailId-1].content}}
          </p>
          <p class="form">新闻来源：{{cardListStory[DetailId-1].source}}&nbsp;摄影：{{cardListStory[DetailId-1].photographer}}&nbsp;责任编辑：{{cardListStory[DetailId-1].editor}}&nbsp;审核:{{cardListStory[DetailId-1].reviewer}}</p>
        </div>

        <div v-else>
<!--           <h1>傻逼</h1> -->
          <h1 class="heading">{{cardListNew[DetailId-1].title}}</h1>
          <hr class="heading-hr">
          <p class="info">发布者：E新向党实践团 发布时间：2024-7-28</p>
          <!-- <video src="../assets/videos/video-01.mp4" autoplay controls :width="640" :height="360"></video> -->
          <img class="textimg" src="../assets/images/CUMT-view1.jpg" alt="笑脸">
          <span class="textexp">笑脸</span>
          <p class="text">
            {{cardListNew[DetailId-1].content}}
          </p>
          <p class="form">新闻来源：{{cardListNew[DetailId-1].source}}&nbsp;摄影：{{cardListNew[DetailId-1].photographer}}&nbsp;责任编辑：{{cardListNew[DetailId-1].editor}}&nbsp;审核:{{cardListNew[DetailId-1].reviewer}}</p>
        </div>

      </div>
    </div>
   

    <WebFoot></WebFoot>
    
  </div>
</template>

<script>
import WebHead from '../components/WebHead.vue'
import WebFoot from '../components/WebFoot.vue'
import WebNavigation from '@/components/WebNavigation.vue';
export default {
  components:{
    WebHead,WebFoot,WebNavigation
  },
  created() {
    this.DetailTemple = this.$route.query.temple
    console.log(this.DetailTemple);
    
    this.DetailId = this.$route.query.id
  },
  data() {
    return {
      DetailId : '',
      DetailTemple:'',
      DetailTempleStr:'',
      cardListStory: [
      {
        temple:1,
        id: 1,
        title: '2024年高等学校实验室安全管理培班级有我',
        summary: '本次培训班由江苏省高等教育学会高校实验室研究委员会主办，聚集了来自全省70余所高校的600余人。',
        content: '7月17日至20日，由江苏省高等教育学会高校实验室研究委员会主办，我校承办的2024年高等学校实验室安全管理培训班在徐州召开，来自全省70余所高校600余人参加了本次培训班……',
        source: 'XXX',
        photographer: 'XXX',
        editor: 'XXX',
        reviewer: 'XX'
      },
      {
        temple:1,
        id: 2,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:1,
        id: 3,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:1,
        id: 4,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:1,
        id: 5,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:1,
        id: 6,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:1,
        id: 7,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:1,
        id: 8,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:1,
        id: 9,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:1,
        id: 10,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:1,
        id: 11,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:1,
        id: 12,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      // 你可以继续添加更多的卡片数据对象
    ],
    cardListNew: [
      {
        temple:0,
        id: 1,
        title: '2024年高新闻培班级有我',
        summary: '本次培训班由江苏省高等教育学会高校实验室研究委员会主办，聚集了来自全省70余所高校的600余人。',
        content: '7月17日至20日，由江苏省高等教育学会高校实验室研究委员会主办，我校承办的2024年高等学校实验室安全管理培训班在徐州召开，来自全省70余所高校600余人参加了本次培训班……',
        source: 'XXX',
        photographer: 'XXX',
        editor: 'XXX',
        reviewer: 'XX'
      },
      {
        temple:0,
        id: 2,
        title: '另一篇新闻的标题12321',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:0,
        id: 3,
        title: '另一篇新闻的标题31231',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:0,
        id: 4,
        title: '另一篇新闻的标题12313',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:0,
        id: 5,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:0,
        id: 6,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:0,
        id: 7,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:0,
        id: 8,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:0,
        id: 9,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:0,
        id: 10,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:0,
        id: 11,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      {
        temple:0,
        id: 12,
        title: '另一篇新闻的标题',
        summary: '这篇新闻简述了一个重要的事件，包含关键信息和背景说明。',
        content: '这是另一篇新闻的内容，这里放一些简短的描述或摘要……',
        source: 'YYY',
        photographer: 'YYY',
        editor: 'YYY',
        reviewer: 'YY'
      },
      // 你可以继续添加更多的卡片数据对象
    ]
    }
  }
}
</script>

<style scoped>
* {
    margin: 0px;
    padding: 0px;
}
.body {
    line-height: 1.6;
    background-color: #f4f4f4;
}
.container {
    width: 80%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 5px 5px;
    background-color: white
}
.heading {
  text-align: center;
  font-size: 30px;
  font-family: 楷体;
  color: rgb(30,50,100);
  margin-top: 0;
  font-weight: 700;
}
.heading-hr {
  border: none;
  height: 2px;
  background-color: rgb(30,50,100);
}
.text {
    font-family: 楷体;
    font-size: 20px;
    text-indent: 2em;
}
.form {
    font-family: 宋体;
    font-size: 16px;
    font-weight: 700;
     text-indent: 2em;
}
.info {
    font-size: 14px;
    color: #777;
    text-align: center;
    margin:5px;
}
/* 文本图片和解释文字的CSS样式 */
.textimg {
    display: block;
    margin: auto;
}

.textexp {
    display: flex;
    justify-content: center;
    font-size: 16px;
    font-family: 楷体;
}
</style>