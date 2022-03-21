<template>
  <div class="bg-fa of">
    <section class="container">
      <section class="i-article">
        <div class="fl col-7">
          <section class="mr30">
            <section class="path-wrap txtOf hLh30">
              <a href="index.html" title="首页" class="c-999 fsize14">首页</a>
              \
              <a href="article.html" title="" class="c-999 fsize14">文章列表</a>
              \
              <span class="c-333 fsize14">{{ title }}</span>
            </section>
            <article class="article-infor-box pr20">
              <h3 class="hLh30 txtOf">
                <span class="i-art-title">{{ intro }}</span>
              </h3>
              <section class="hLh30 txtOf mt5 pb20 mreadnum">
                <div class="fr">
                  <span>
                    <a class="noter-dy vam" title="评论" href="#">
                      <em class="icon18">&nbsp;</em>(<span
                        class="totalResultComment"
                        >{{ review }}</span
                      >)
                    </a>
                    <tt
                      title="赞一下"
                      onclick="addPraise('23',3)"
                      class="noter-zan vam ml5 f-fM"
                    >
                      <em class="icon18">&nbsp;</em>(<span
                        class="addPraise23_3 praiseCount"
                        >{{ heart }}</span
                      >)
                    </tt>
                  </span>
                </div>
                <div class="fl pt3">
                  <tt class="c-999 f-fM"> {{ date }}</tt>
                </div>
              </section>
              <div id="art-infor-body">
                <div v-html="htmlToString()"></div>
                <div>
                  <tt class="c-999 f-fM">
                    评论：<span class="totalResultComment">{{ review }}</span>
                  </tt>
                  <tt class="c-999 f-fM ml20">
                    点赞：<span class="addPraise23_3 praiseCount">{{
                      heart
                    }}</span>
                  </tt>
                  <tt class="c-999 f-fM ml20">
                    阅读：<span class="clickNum">{{ yuedu }}</span>
                  </tt>
                </div>
              </div>
            </article>
          </section>
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
        <div class="clear"></div>
      </section>
    </section>
    <!-- /文章列表 结束 -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      paihang: [
        {
          id: 1,
          mingci: 1,
          path: "/article/1",
          title: "中国军舰协助英、德等10国从也门撤侨225人",
          review: 2,
          heart: 3,
          date: "2019-02-26 10:31",
        },
        {
          id: 2,
          mingci: 2,
          path: "/article/2",
          title: "中国军舰协助英、德等10国从也门撤侨225人",
          review: 2,
          heart: 3,
          date: "2019-02-26 10:31",
        },
        {
          id: 3,
          mingci: 3,
          path: "/article/1",
          title: "中国军舰协助英、德等10国从也门撤侨225人",
          review: 2,
          heart: 3,
          date: "2019-02-26 10:31",
        },
        {
          id: 4,
          mingci: 4,
          path: "/article/1",
          title: "中国军舰协助英、德等10国从也门撤侨225人",
          review: 2,
          heart: 3,
          date: "2019-02-26 10:31",
        },
        {
          id: 5,
          mingci: 5,
          path: "/article/1",
          title: "中国军舰协助英、德等10国从也门撤侨225人",
          review: 2,
          heart: 3,
          date: "2019-02-26 10:31",
        },
        {
          id: 6,
          mingci: 6,
          path: "/article/1",
          title: "中国军舰协助英、德等10国从也门撤侨225人",
          review: 2,
          heart: 3,
          date: "2019-02-26 10:31",
        },
        {
          id: 6,
          mingci: 6,
          path: "/article/1",
          title: "中国军舰协助英、德等10国从也门撤侨225人",
          review: 2,
          heart: 3,
          date: "2019-02-26 10:31",
        },
      ],
      title: "雅思阅读能力提高有方法 文章精读可以这样做",
      intro: "雅思阅读能力提高有方法 文章精读可以这样做",
      review: 3,
      heart: 100,
      yuedu: 200,
      date: "2019-02-26 10:31",
      content:""
    };
  },
  methods: {
    judge(index) {
      if (index == 0 || index == 1 || index == 2) {
        return true;
      } else {
        return false;
      }
    },
    htmlToString() {
      var text = "";
      text += "";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text +=
        '										关于<a class="a-tips-Article-QQ" href="http://edu.qq.com/kszx/ielts.shtml" style="outline:none;color:#000000;text-decoration:none;border-bottom-width:1px;border-bottom-style:dotted;border-bottom-color:#536DA6;">雅思</a>(<a target="_blank" href="http://class.qq.com/category/94.html" class="a-tips-Article-QQ" style="outline:none;color:#000000;text-decoration:none;border-bottom-width:1px;border-bottom-style:dotted;border-bottom-color:#536DA6;">课程</a>)精读，首先，认真选择精读文章，只需10篇剑桥文章，你的成绩就可以在7.5以上。但这一前提是你不是流于形式，而是认真走心的读。';
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text += "										我一直认为雅思精读最大的目的在于四点：";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text += "										1、生词+学科核心生词";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text += "										2、每道题涉及解题的同义替换";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text += "										3、长难句的不回读训练";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text += "										4、段落中心句位置+文章构架的积累训练与开悟体验";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text += "										1、生词+学科核心生词";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text +=
        "										雅思考生公认精读来扫清阅读单词死角是再合适不过的了，尤其精读了几篇生物类文章，再答生物类全都认识了。比如C7蚂蚁智能里面的forage/scout/bearing/odour等词，精读过少量生物类文章，再去做OG上的swarm之类的文章就非常easy了，通篇可以快速读懂，准确定位，正确率超高。";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text +=
        "										再如精读过C9的金星凌日，天文类词汇基底你就get到了，什么日食月食轨道运行太阳黑子与光斑，只要考试出了天文类，百分之75以上的基底词汇你都是认识的，答题就自如多了。";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text += "										2、每道题涉及解题的同义替换";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text +=
        "										粗定位一个定位词，全文可能会出现30多处，俗话说：两点定一线，你的关键词/定位词，至少要画两个以上还要全都找到。我一般建议学生“抓三点”“抓四点”“抓五点”，题配句，词换词，细定位就是要找至少两三个换的词。";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text +=
        "										说到底，同义替换词这个事情，还是要多多积累的，比积累词汇量在雅思阅读中，还要重要。";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text += "										所以单词量达到瓶颈以后，要做的是背”同义替换词表“";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text += "										3、长难句的不回读训练";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text += "										忘了是哪个老师说三行以上必出题。";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text +=
        "										N个学生的反馈都是：长难句读到后半句，前面就忘了度过了什么。或者单词都认识，就是读文章速度太慢。";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text +=
        "										当年考GMAT看过一本《GMAT长难句练习》，里面提到了”打死我也不回读”这个方法，一直分享给学生，效果反馈很棒。里面说：";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text +=
        "										只要每天练习五个长难句不回读训练，看到大长句子，习惯性切割主谓宾，一周就会看到效果。本来想着不就是主谓宾嘛，结果练了十多天，读题速度有了飞跃性的提升。";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text +=
        "										长难句再也不是问题，看到就自动读主谓宾，这就可以轻松记住意思，读下面句子的时候，逻辑就形成了非常舒服的衔接。如果有题在句子中，再去精读也不迟。";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text += "										4、段落中心句位置+文章构架的积累训练与开悟体验";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text += "										LOH和 段落信息配对，怎么做，主要靠精读的这个步骤。";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text +=
        "										LOH做多了，自然有了feel，首句中心句?末句中心句?转折中心句?这就不细说了，做多了就知道。";
      text += "									</p>";
      text +=
        '									<p style="margin-top:0px;margin-bottom:29px;padding:0px;line-height:28px;font-family:宋体, Arial, sans-serif;font-size:15.9996px;white-space:normal;text-indent:2em;background-color:#FFFFFF;">';
      text +=
        "										段落信息配对题，因为无序且恶心，同义替换幅度较大，有时候需要通读全文。我却始终坚信“预测乃解决断子绝孙题的直通车”。只要精读了，你就会发现，原来文章各个部位都有暗示你过，那么下次如果你没读原文直接做MATCHING你要怎么“蒙题”，精读多了你就懂了";
      text += "									</p>";
      text += "";
      text += "							";
      return text;
    },
  },
  components: {},

  computed: {},
};
</script>
<style scoped>
</style>