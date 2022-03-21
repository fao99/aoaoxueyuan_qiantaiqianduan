<template>
  <div id="aCoursesList" class="bg-fa of">
    <section class="container">
      <section class="i-article">
        <div class="fl col-7 right">
          <header class="comm-title">
            <h2 class="fl tac">
              <span class="c-333">文章</span>
            </h2>
          </header>
          <article class="i-article-list">
            <ul>
              <li v-for="item in article" :key="item.id">
                <aside class="i-article-pic">
                  <img :src="item.imgurl" alt="" />
                </aside>
                <h3 class="hLh30 txtOf">
                  <a
                    :href="item.path"
                    :title="item.title"
                    class="i-art-title"
                    >{{ item.title }}</a
                  >
                </h3>
                <section class="i-q-txt mt5 i-q-txt2">
                  <p>
                    <span class="c-999 f-fA">{{ item.intro }}</span>
                  </p>
                </section>
                <section class="hLh30 txtOf mt5 pr10 a-list-extrainfo">
                  <span class="fr"
                    ><tt class="c-999 f-fM">{{ item.date }}</tt></span
                  >
                  <div class="fl">
                    <span>
                      <a class="noter-dy vam" title="回答" href="#">
                        <em class="icon18">&nbsp;</em>(<span>{{
                          item.review
                        }}</span
                        >)
                      </a>
                      <tt
                        title="赞一下"
                        class="noter-zan vam ml10 f-fM"
                      >
                        <em class="icon18">&nbsp;</em>(<span
                          class="addPraise23_3 praiseCount"
                          >{{ item.heart }}</span
                        >)
                      </tt>
                    </span>
                  </div>
                </section>
              </li>
            </ul>
            <!-- /文章列表 结束-->
          </article>
        </div>
        <aside class="fl col-3 articleRecommend">
          <div>
            <header class="comm-title all-article-title">
              <h2 class="fl tac">
                <span class="c-333">文章排行榜</span>
              </h2>
              <section class="c-tab-title">
                <a href="javascript: void(0)">&nbsp;</a>
              </section>
            </header>
            <section class="i-article-list r-art-wrap">
              <ul>
                <li
                  v-for="(item, index) in paihang"
                  :key="item.id"
                  :class="{ lt2: judge(index) }"
                >
                  <aside class="orderNum">
                    <span>{{ item.mingci }}</span>
                  </aside>
                  <h3 class="hLh30 txtOf">
                    <a
                      :href="item.path"
                      :title="item.title"
                      class="i-art-title"
                      >{{ item.title }}</a
                    >
                  </h3>
                  <section class="hLh30 txtOf mt5">
                    <div class="fr">
                      <span>
                        <a class="noter-dy vam" title="回答" href="#">
                          <em class="icon18">&nbsp;</em>({{ item.review }})
                        </a>
                        <tt
                          title="赞一下"
                          class="noter-zan vam ml10 f-fM"
                          onclick="addPraise('23',3)"
                        >
                          <em class="icon18">&nbsp;</em>(<span
                            class="addPraise23_3 praiseCount"
                            >{{ item.heart }}</span
                          >)
                        </tt>
                      </span>
                    </div>
                    <span class="fl"
                      ><tt class="c-999 f-fM">{{ item.date }}</tt></span
                    >
                  </section>
                </li>
              </ul>
            </section>
          </div>
        </aside>
      </section>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      article: [
        {
          id: 1,
          title: "雅思阅读能力提高有方法 文章精读可以这样做",
          intro:
            "　在各门科目之中，有两门课程是拉分最多的，一门是数学，一门是英语。其中英语是在多数考生最大的拦路虎，因为工作多年的人，如果工作中不常接触，英语的底子多是很差的。而英语是很难突击上去的，靠临时“抱佛脚”很难奏效。我英语基础较差，但经过自己有计划、有重点的系统复习，年MBA[微博]联考中，英语过了70分这道槛，取得了较为满意的结果，感到甚是欣慰。",
          review: 1,
          heart: 1,
          imgurl: require("../../assets/photo/article/01.jpg"),
          date: "2019-02-26 10:31",
          path: "/article/1",
        },
        {
          id: 2,
          title: "上海阿爸”张志勇帮困助学近20年，只为让山里学生过上好日子",
          intro:
            "64岁的“上海阿爸”张志勇得知成为第七批全国岗位学雷锋标兵时，正带领着上海医疗队在云南泸西为当地癫痫儿童义诊：“我只是一个爱心接力的‘火炬手’，这个荣誉不是我自己的，它属于上海的每一个好心人。",
          review: 2,
          heart: 1,
          imgurl: require("../../assets/photo/article/02.jpg"),
          date: "2019-02-26 10:31",
          path: "/article/2",
        },
        {
          id: 3,
          title: "外交部辟谣美方称对疫情提供巨大帮助",
          intro:
            "美方表示，美方已为中方应对疫情提供了巨大帮助。对于美方究竟有没有向中方提供援助？中国外交部发言人华春莹今天作出回应",
          review: 1,
          heart: 3,
          imgurl: require("../../assets/photo/article/03.jpg"),
          date: "2019-02-26 10:31",
          path: "/article/3",
        },
        {
          id: 4,
          title: "市教委：五项举措强化校园疫情防控",
          intro:
            "为认真贯彻落实3月12日全国疫情防控工作电视电话会议精神，结合我市当前校园疫情严峻形势，为进一步加强校园疫情防控，现就有关工作通知如下",
          review: 1,
          heart: 2,
          imgurl: require("../../assets/photo/article/04.jpg"),
          date: "2019-02-26 10:31",
          path: "/article/4",
        },
      ],
      paihang: [
        {
          id: 1,
          mingci: 1,
          path: "/article/1",
          title: "外交部辟谣美方称对疫情提供巨大帮助",
          review: 2,
          heart: 3,
          date: "2019-02-26 10:31",
        },
        {
          id: 2,
          mingci: 2,
          path: "/article/2",
          title: "市教委：五项举措强化校园疫情防控",
          review: 2,
          heart: 3,
          date: "2019-02-26 10:31",
        },
        {
          id: 3,
          mingci: 3,
          path: "/article/1",
          title: "雅思阅读能力提高有方法 文章精读可以这样做",
          review: 2,
          heart: 3,
          date: "2019-02-26 10:31",
        },
        {
          id: 4,
          mingci: 4,
          path: "/article/1",
          title: "上海阿爸”张志勇帮困助学近20年，只为让山里学生过上好日子",
          review: 2,
          heart: 3,
          date: "2019-02-26 10:31",
        }
      ],
    };
  },

  components: {},

  computed: {},

  methods: {
    judge(index) {
      if (index == 0 || index == 1 || index == 2) {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>
<style scoped>

</style>
