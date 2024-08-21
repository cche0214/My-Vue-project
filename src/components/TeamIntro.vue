<template>
  <div class="team-intro-container">
    <div class="heading">实践团介绍</div>
    <hr class="heading-hr" />

    <div class="images-grid">
      <div v-for="(image, index) in images" :key="index" class="image-item">
        <img :src="require(`@/assets/images/${image.src}`)" :alt="image.alt" />
        <p>{{ image.description }}</p>
      </div>
    </div>

    <div class="intro-text">
      <span>
        中国矿业大学是教育部直属的全国重点高校，是教育部、应急管理部与江苏省人民政府共建高校，先后进入国家“211工程”“985优势学科创新平台项目”和国家“双一流”建设高校行列。
        学校为全国首批具有博士和硕士授予权的高校之一，设有国家批准的研究生院。
        学校现坐落于素有“五省通衢”之称的国家历史文化名城——江苏省徐州市，有文昌和南湖两个校园，占地4200余亩，校舍建筑面积156万平方米，馆藏图书文献2000多万册（件）。
        学校现有2个国家“双一流”建设学科、1个一级学科国家重点学科，8个二级学科国家重点学科，1个国家重点（培育）学科；7个江苏省优势学科、7个江苏省重点学科；
        18个一级学科博士点，2个专业学位博士点，36个一级学科硕士点，20个专业学位硕士点。
        学校设23个学院，74个本科专业，有全日制普通本科生23600余人，各类博士、硕士研究生13300余人，留学生680余人，继续教育学生10000余人；
        有教职工3450余人；另设有徐海学院。
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "TeamIntro",
  data() {
    return {
      images: [
        { src: "CUMT-view1.jpg", alt: "团队照片1", description: "实践团前往某地进行实践实践团前往某地进行实践" },
        { src: "CUMT-view2.jpg", alt: "团队照片2", description: "实践团前往某地进行实践实践团前往某地进行实践" },
        { src: "CUMT-view3.jpg", alt: "团队照片3", description: "实践团前往某地进行实践实践团前往某地进行实践实践团前往某地进行实践" },
        { src: "CUMT-view4.jpg", alt: "团队照片4", description: "中实践团前往某地进行实践实践团前往某地进行实践实践团前往某地进行实践实践团前往某地进行实践" },
      ],
    };
  },
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
.team-intro-container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
}
.images-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(2, 1fr);
}
.image-item {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.image-item img {
  width: 98%;
  max-width: 100%;
  height: auto;
  object-fit: cover;
  border-radius:20px
}

.image-item p {
  margin-top: 2px;
  font-size: 12px;
  text-align: center;
  font-family: 楷体;
}

.intro-text {
    width: 98%;
    font-family: 楷体;
    box-sizing: border-box;
    margin: 0 auto;
    text-indent: 2em;
    border: 2px solid rgb(30,50,100);
    border-radius: 15px;
    background-color: rgba(30, 50, 100,0.6);
    color: white;
    line-height: 1.6;
    font-size: 18px;
}
</style>
