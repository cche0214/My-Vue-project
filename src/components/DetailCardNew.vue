<template>
  <!-- 卡片容器 -->
<div class="card-list">
    <!-- 卡片 -->
    <div class="card" v-for="card in cardListNew" :key="card.id">
        <div class="content">
            <h2>{{ card.title }}</h2>
            <p>{{ card.summary }}</p>
            <a :href="card.link" class="button" @click="$router.push(`/detail?id=${card.id}&temple=${card.temple}`)">查看更多</a>
        </div>
    </div>
</div>

 
</template>

<script>
export default {
  data() {
  return {
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
        temple:0,
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
  };
}

}
</script>

<style scoped>
.card-list {
    display: flex;
    flex-wrap: wrap; /* 允许换行 */
    justify-content: space-between; /* 在每行中均匀分布卡片 */
}

.card {
  position: relative;
    width: 240px;
    height: 350px;
    margin: 10px;
    display: flex;
    align-items: flex-end;
    text-align: center;
    color: #f5f5f5;
    box-shadow: 0 1px 1px rgba(0,0,0,0.1),
                0 2px 2px rgba(0,0,0,0.1),
                0 4px 4px rgba(0,0,0,0.1),
                0 8px 8px rgba(0,0,0,0.1),
                0 16px 16px rgba(0,0,0,0.1);
    overflow: hidden;
    background-color: transparent; /* 确保背景颜色为透明 */
}

.card::before {
  content: "";
    width: 100%;
    height: 110%;
    position: absolute;
    top: 0;
    left: 0;
    background-size: cover;
    background-position: 0 0;
    transition: transform 1s cubic-bezier(0.19,1,0.22,1);
}
.card:nth-child(1)::before {
    background-image: url('../assets/images/CUMT-view1.jpg');
}
.card:nth-child(2)::before {
    background-image: url('../assets/images/CUMT-view2.jpg');
}
.card:nth-child(3)::before {
    background-image: url('../assets/images/CUMT-view3.jpg');
}
.card:nth-child(4)::before {
    background-image: url('../assets/images/CUMT-view4.jpg');
}
.card:nth-child(5)::before {
    background-image: url('../assets/images/CUMT-view1.jpg');
}
.card:nth-child(6)::before {
    background-image: url('../assets/images/CUMT-view3.jpg');
}
.card:nth-child(n+6)::before {
    background-image: url('../assets/images/CUMT-view1.jpg');
}
.card::after {
  content: "";
    display: block;
    width: 100%;
    height: 200%;
    background: linear-gradient(to bottom, rgba(0,0,0,0) 0%, rgba(0,0,0,0.25) 55%, rgba(0,0,0,0.8) 100%);
    position: absolute;
    left: 0;
    top: 0;
    transform: translateY(0);
    transition: transform 1.4s cubic-bezier(0.19,1,0.22,1);
}
.card .content {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    z-index: 1;
    padding: 16px 8px;
    transform: translateY(76%);
    transition: transform 0.7s cubic-bezier(0.19,1,0.22,1);
}
.card h2 {
    font-size: 20px; 
    font-weight: bold;
    width: calc(100% - 20px);
    text-align: center;
    overflow-wrap: break-word; 
    margin: 10px 0; 
    padding: 0 10px; 
}
.card p {
    font-size: 15px;
    letter-spacing: 2px;
    width: 80%;
    line-height: 30px;
    margin-top: 25px;
    text-align: justify;
}
.card .button {
    display: inline-block;
    cursor: pointer;
    border: none;
    background-color: rgba(0, 0, 0, 0.5);
    color: #fff;
    padding: 12px 24px;
    font-size: 12px;
    font-weight: bold;
    margin-top: 25px;
    text-decoration: none;
    text-align: center;
}
.card .button:hover {
    background-color: #000;
}
.card .content *:not(h2) {
    opacity: 0;
    transform: translateY(20px);
    transition: transform 0.7s cubic-bezier(0.19,1,0.22,1), opacity 0.7s cubic-bezier(0.19,1,0.22,1);
}
.card:hover {
    align-items: center;
}
.card:hover::before {
    transform: translateY(-5%);
}
.card:hover::after {
    transform: translateY(-50%);
}
.card:hover .content {
    transform: translateY(0);
}
.card:hover .content *:not(h2) {
    opacity: 1;
    transform: translateY(0);
    transition-delay: 0.1s;
}
</style>