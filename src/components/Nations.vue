<template>
  <div>
    <div @contextmenu.prevent class="card-list">
      <a
        @mousedown.left="openDetail(nation)"
        @mousedown.right="handleShowCapital(nation)"
        href="#"
        class="card-item"
        v-for="nation in nations"
        :key="nation"
      >
        <h3>{{ nation.name }}</h3>
        <img :src="nation.flag" alt="Card Image" />
        <h3 v-if="nation.showCapital" class="capital">{{ nation.capital }}</h3>
      </a>
    </div>
    <NationDetail :selected="selected" :showDetail="showDetail" @closeDetail="showDetail=false"/>
  </div>
</template>
<script>
import NationDetail from "./NationDetail.vue";

export default {
  components: {
    NationDetail,
  },
  data() {
    return {
      nations: [
        {
          name: "미국",
          capital: "워싱턴D.C",
          showCapital: false,
          description:
            "미합중국(한국 한자: 美合眾國, 영어: United States of America, USA) 또는 대중적으로 미국(한국 한자: 美國, 문화어: 미국(한국 한자: 米國), 영어: America)은 주 50개와 특별구 1개로 이루어진 연방제 공화국이다. 태평양에 위치한 하와이를 제외한 모든 주와 수도인 워싱턴 D.C.는 북아메리카 대륙에 위치하며, 북쪽으로는 캐나다와 남쪽으로는 멕시코와 국경을 맞닿는다. 또한 북아메리카 북서측에 있는 알래스카는 동측으로는 캐나다와 서측으로는 베링 해협을 사이로 러시아와 마주한다. 미국은 태평양과 카리브해에 해외 영토를 보유한다.",
          flag: "https://i.namu.wiki/i/Dj_I51HG6tAfOvWyq7GV0RsxqKuRIB59GKetL-FebRS0ydGqU6K_XSoszMrVnY4L54PxXdkzF36O7gKjU7FSNA.svg",
          symbol:
            "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRnWCppB2a5crK1VisGPF27RUVctA7VVztDHusR97h2StTaP5O-3Y0iJU1YJMB2XIAL8lg&usqp=CAU",
        },
        {
          name: "영국",
          capital: "런던",
          showCapital: false,
          description:
            "그레이트브리튼 북아일랜드 연합왕국[주 2], 약칭 영국[주 3]은 유럽 본토 해안에서 북서쪽으로 떨어진 곳에 위치한 섬나라이자 입헌군주국이다. 북해, 영국 해협, 아일랜드해 및 대서양에 접하여 있으며 그레이트브리튼섬의 잉글랜드, 스코틀랜드, 웨일스 및 아일랜드섬 북부의 북아일랜드로 네 개의 구성국이 연합해 형성한 단일 국가이다.[주 4] 수도는 런던이고 스코틀랜드, 웨일스, 북아일랜드의 수도는 각각 에든버러, 카디프, 벨파스트이다.",
          flag: "https://i.namu.wiki/i/WNw8JiSr4x94S6McVTaDj70J_VmBtOPAV6NzP5FBOyRXD7E7nalYplrZeyGtsKq8KyAezsTqtS3Uec3jchRRUw.svg",
          symbol:
            "https://blog.kakaocdn.net/dn/rU8ez/btrYRTWGebd/mKlift0gwVzBRmeacCkb4k/img.png",
        },
        {
          name: "독일",
          capital: "베를린",
          showCapital: false,
          description:
            "독일연방공화국[f], 약칭 독일[g]은 중앙유럽에 위치한 국가이다. 인구는 2022년 기준 83,695,430명으로 유럽[h]에서 러시아에 이어 두 번째로 인구가 많은 나라이자 유럽연합(EU) 회원국 중 인구가 가장 많은 국가이다. 독일은 북쪽으로 발트해, 북해와 남쪽으로 알프스 산맥의 사이에 위치하며, 북쪽으로 덴마크, 동쪽으로 폴란드와 체코, 남쪽으로 오스트리아와 스위스, 서쪽으로는 베네룩스 3국[i]과 프랑스와 접해 있다. 독일의 영토는 357,021km2이며, 기후는 주로 온대 기후를 보인다. 공용어는 독일어이고, 그 외에 소수 민족들의 언어인 러시아어, 영어, 소르브어, 덴마크어, 프리지아어 등도 쓰인다. 독일의 수도이자 가장 인구가 많은 도시는 베를린이고, 주요 금융 중심지는 프랑크푸르트, 가장 넓은 도시권은 루르이다.",
          flag: "https://i.namu.wiki/i/KiykE29mubKM3qGGIT5i3xubJFilCDaC-6R0j4WUCbTVYIeHYqw8zAhidpwGhlBI7T2zHpdS4tjqSgvrcITPEw.svg",
          symbol: "https://img.hankyung.com/photo/201408/AA.8955478.1.jpg",
        },
      ],
      showDetail: false,
      selected: null,
    };
  },
  methods: {
    handleShowCapital(nation) {
      nation.showCapital = !nation.showCapital;
    },
    openDetail(nation) {
      this.selected = nation;
      this.showDetail = true;
    },
  },
};
</script>
<style>
/* Importing Google font - Open Sans */
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;500;600;700&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Open Sans", sans-serif;
}

body {
  background: #ecececdb;
  display: block;
}

button {
  background-color: #fff;
  width: 20%;
  margin: 0;
  padding: 0.5rem 1rem;
  font-size: 1rem;
  font-weight: 900;
  text-align: center;
  border-radius: 4px;
  cursor: pointer;
}

div {
  margin-top: 20px;
  width: 100%;
  text-align: center;
}
.card-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  max-width: 1250px;
  margin: 150px auto;
  margin-top: 0px;
  margin-bottom: 0px;
  padding: 20px;
  gap: 20px;
}

.card-list .card-item {
  background: #fff;
  padding: 50px;
  border-radius: 8px;
  box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.04);
  list-style: none;
  cursor: pointer;
  text-decoration: none;
  border: 2px solid transparent;
  transition: border 0.5s ease;
}

.card-list .card-item:hover {
  border: 2px solid #000;
}

.card-list .card-item img {
  margin-top: 20px;
  width: 100%;
  aspect-ratio: 16/9;
  border-radius: 8px;
  object-fit: cover;
}

.card-list span {
  display: inline-block;
  background: #f7dff5;
  margin-top: 32px;
  padding: 8px 15px;
  font-size: 0.75rem;
  border-radius: 50px;
  font-weight: 600;
}
.card-item h3 {
  color: #000;
  font-size: 1.438rem;
  /* margin-top: 28px; */
  font-weight: 600;
  text-align: center;
}
.capital {
  background-color: yellow;
}

.nation-detail {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
}

.nation-detail > div {
  position: absolute;
  top: 5%;
  left: 25%;
  background: white;
  border-radius: 20px;
  height: 80%;
  width: 50%;
  padding-left: 5%;
  padding-right: 5%;
  text-align: left;
}
.nation-detail span {
  position: absolute;
  right: 30px;
  cursor: pointer;
}
.nation-detail img {
  margin-top: 10px;
  margin-bottom: 10px;
  width: 100%;
  height: 40%;
}

@media (max-width: 1200px) {
  .card-list .card-item {
    padding: 15px;
  }
}

@media screen and (max-width: 980px) {
  .card-list {
    margin: 0 auto;
  }
}
</style>
