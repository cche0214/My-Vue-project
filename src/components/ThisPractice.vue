<template>
  <div>
    <div class="heading">本次实践</div>
    <hr class="heading-hr" />

    <div class="practice">
      <div class="images">
        <img src="@/assets/images/CUMT-view1.jpg" alt="Image 1" />
        <img src="@/assets/images/CUMT-view4.jpg" alt="Image 2" />
      </div>
      <div class="stats">
        <div
          class="number-container"
          style="border: 2px solid rgb(30, 50, 100)"
        >
          <p>
            中国矿业大学是教育部直属的全国重点高校，是教育部、应急管理部与江苏省人民政府共建高校，
            先后进入国家“211工程”“985优势学科创新平台项目”和国家“双一流”建设高校行列。
            学校为全国首批具有博士和硕士授予权的高校之一。学校为全国首批具有博士和硕士授予权的高校之一。
            学校为全国首批具有博士和硕士授予权的高校之一。学校为全国首批具有博士和硕士授予权的高校之一。
            学校为全国首批具有博士和硕士授予权的高校之一。
          
          </p>
        </div>
        <div
          class="number-container"
          v-for="(stat, index) in stats"
          :key="index"
          @click="increment(stat)"
        >
          <span class="description">{{ stat.description }}</span>
          <span class="number-display">{{ stat.displayNumber }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      stats: [
        { description: '累计实践地区', end: 86, displayNumber: '???' },
        { description: '累计实践地区', end: 50, displayNumber: '???' },
        { description: '累计实践地区', end: 97, displayNumber: '???' }
      ]
    };
  },
  methods: {
    increment(stat) {
      let start = 1;
      const end = stat.end;
      stat.displayNumber = ''; // 清空显示内容
      const interval = setInterval(() => {
        start += 2;
        if (start > end) {
          clearInterval(interval);
          stat.displayNumber = end.toLocaleString();
        } else {
          stat.displayNumber = start.toLocaleString();
        }
      }, 10);
    }
  }
};
</script>

<style scoped>
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
  margin-bottom: 15px;
}
.practice {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.images {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.images img {
  border: 2px solid rgb(30, 50, 100);
  width: 700px;
  height: 320px;
  object-fit: cover;
  border-radius: 8px;
}

.stats {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 15px;
  width: 100%;
}

.stats p {
  font-family: 楷体;
  font-size: 20px; /* 字体大小增大 */
  color: white;
  text-indent: 2em;
}

.number-container {
  border-radius: 10px;
  background-color: rgb(30, 50, 100);
  display: flex;
  align-items: center;
  justify-content: space-between; /* 在number-container中左右对齐 */
  gap: 5px;
  padding: 10px;
  width: 90%;
  max-width: 600px;
}

.number-container:nth-child(2n+1) {
  background-color: rgba(30, 50, 100, 0.6);
}

.number-container:nth-child(2),
.number-container:nth-child(3),
.number-container:nth-child(4) {
  cursor: pointer; /* 设置光标为可点击样式 */
}

.description {
  font-family: 楷体;
  font-size: 18px; /* 字体大小增大 */
  color: white;
  flex: 1; /* 占据左侧的空间 */
  text-align: left; /* 左对齐 */
  
}

.number-display {
  font-size: 26px; /* 字体大小略微增大 */
  font-weight: bold;
  color: white;
  flex-shrink: 0; /* 避免数字被压缩 */
  text-align: right;
}
</style>
