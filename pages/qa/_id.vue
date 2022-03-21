<template>
  <div class="bg-fa of">
    <section class="container">
      <section class="i-question">
        <div class="fl col-7">
          <section class="mr30 pt10">
            <section class="path-wrap txtOf hLh30">
              <a href="http://127.0.0.1:81" title="" class="c-999 fsize14"
                >首页</a
              >
              \
              <a
                href="http://127.0.0.1:81/questions/list"
                title=""
                class="c-999 fsize14"
                >全部问答</a
              >
              \
              <span class="c-333 fsize14">{{ title }}</span>
            </section>
            <div>
              <section class="q-infor-box">
                <div class="pr">
                  <aside class="q-head-pic">
                    <img :src="userImg" alt="" />
                    <p class="hLh30 txtOf"></p>
                  </aside>
                  <section class="q-txt-box">
                    <h3 class="hLh30 txtOf">
                      <em class="icon16 q-tw">&nbsp;</em>
                      <span class="c-blue fsize14"> {{ raiser }}</span>
                      <span class="c-999 fsize14"> 课程提问</span>
                    </h3>
                  </section>
                  <section class="ml50 pl10">
                    <div class="mt20">
                      <h3 class="hLh30 txtOf">
                        <span class="fsize18 c-333 vam">{{ title }}</span>
                      </h3>
                    </div>
                    <div class="i-q-txt mt15">
                      <span class="c-999 f-fA">{{ content }}</span>
                    </div>
                    <div class="mt20 pr10">
                      <section class="fr">
                        <span>
                          <a
                            href="#i-art-comment"
                            title="评论"
                            class="noter-dy vam"
                          >
                            <em class="icon18">&nbsp;</em>(<span
                              id="questionsReplyCount"
                              >1</span
                            >)
                          </a>
                          <tt
                            class="noter-zan vam ml10 f-fM"
                            title="赞一下"
                            onclick="addPraise(9,1,this)"
                          >
                            <em class="icon18">&nbsp;</em>(<span>2</span>)
                          </tt>
                        </span>
                      </section>
                      <span class="c-ccc fl vam">{{ date }}</span>
                      <section class="fl ml20 pt10">
                        <div class="taglist clearfix">
                          <a
                            title="Premiere"
                            data-id="5"
                            onclick="submitForm('5','questionsTagId')"
                            class="list-tag"
                            href="javascript:;"
                            >{{ type }}</a
                          >
                        </div>
                      </section>
                      <div class="clear"></div>
                    </div>
                  </section>
                </div>
                <span id="questionsCommentSpan"
                  ><!-- /最佳答案 开始-->
                  <div class="good-anwer-box">
                    <h4 class="g-a-title">
                      <span class="bg-green vam"
                        ><em class="icon24 mr5">&nbsp;</em>最佳答案</span
                      >
                    </h4>
                    <section class="good-answer mt10">
                      <section class="question-list lh-bj-list pr">
                        <ul class="pr10">
                          <li>
                            <aside class="noter-pic">
                              <img
                                src="../../assets/photo/customer/03.jpg"
                                alt=""
                                width="50"
                                height="50"
                              />
                            </aside>
                            <div class="of hLh20">
                              <span class="fl">
                                <font class="fsize12 c-blue">学员2</font>
                                <font class="fsize12 c-999 ml5"
                                  >回复：</font
                                ></span
                              >
                            </div>
                            <div class="noter-txt mt5">
                              <p>
                                premiere是一款常用的视频编辑软件，由Adobe公司推出。现在常用的有CS4
                                CS5
                                CS6等版本。是一款编辑画面质量比较好的软件，有较好的兼容性，且可以与adobe公司推出的其他软件相互协作。目前这款软件广泛应用于广告制作和电视节目制作中。
                                其最新版本为Adobe Premiere Pro CC。
                              </p>
                            </div>
                            <div class="of mt5">
                              <span class="fr"
                                ><font class="fsize12 c-999 ml5"
                                  >2015-09-19 10:15</font
                                ></span
                              >
                              <span class="fl">
                                <a
                                  href="javascript: void(0)"
                                  title="回答"
                                  class="noter-dy vam"
                                  onclick="getCommentById(this,12)"
                                >
                                  <em class="icon18">&nbsp;</em
                                  >全部评论(<span>0</span>)
                                </a>
                                <tt
                                  class="noter-zan vam ml10 f-fM"
                                  title="赞一下"
                                  onclick="addPraise(12,2,this)"
                                >
                                  <em class="icon18">&nbsp;</em
                                  >点赞(<span>0</span>)
                                </tt>
                              </span>
                            </div>
                            <div class="n-reply">
                              <section class="n-reply-wrap mt10">
                                <fieldset>
                                  <textarea
                                    name=""
                                    placeholder="输入您要评论的文字"
                                    id="commentContent"
                                  ></textarea>
                                </fieldset>
                                <p class="of mt5 tar pl10 pr10">
                                  <span class="fl"
                                    ><tt
                                      class="c-red commentContentmeg"
                                      style="display: none"
                                    ></tt
                                  ></span>
                                  <a
                                    href="javascript:addComment();"
                                    title="回复"
                                    class="lh-reply-btn"
                                    >回复</a
                                  >
                                </p>
                              </section>
                              <input type="hidden" id="" name="" value="12" />
                              <div class="mt10 pl10 pr10">
                                <dl class="n-reply-list">
                                  <!-- 最佳答案的评论在这里 -->
                                </dl>
                              </div>
                            </div>
                            <!-- /回复盒子 -->
                          </li>
                        </ul>
                      </section>
                    </section>
                  </div>
                  <!-- /最佳答案 结束-->
                  <!-- /回答列表 开始 -->
                  <div class="q-i-noter-box">
                    <section class="q-i-reply">
                      <h6 class="c-c-content c-infor-title">
                        <span>问答列表</span>
                      </h6>
                    </section>
                    <!-- /无数据提示 开始-->
                    <section class="no-data-wrap">
                      <em class="icon30 no-data-ico">&nbsp;</em>
                      <span class="c-666 fsize14 ml10 vam"
                        >还没有人回答，提问者喊你去回答...</span
                      >
                    </section>
                    <!-- /无数据提示 结束-->
                  </div>
                </span>
              </section>
            </div>
            <!-- /问题列表 结束 -->
          </section>
        </div>
        <aside class="fl col-3">
          <div class="mt30 pl10">
            <section class="pt10">
              <a
                href="javascript:void(0)"
                onclick="toAddQuestions()"
                title="我要提问"
                class="comm-btn c-btn-5"
                >我要提问</a
              >
            </section>
            <section class="pt20">
              <div class="taglist clearfix">
                <a
                  v-for="item in questionTypes"
                  onclick=""
                  href="javascript:;"
                  class="list-tag"
                  :data-id="item.id"
                  :title="item.type"
                  :key="item.id"
                  >{{ item.type }}</a
                >
              </div>
            </section>
            <!-- /标签云 -->
            <section class="mt30">
              <section class="c-infor-tabTitle c-tab-title">
                <a href="javascript: void(0)" title="热门问答推荐"
                  >热门问答推荐</a
                >
              </section>
              <div class="q-r-rank-list">
                <ul id="hotQuestions">
                  <li v-for="item in hotQuestionList" :key="item.id">
                    <aside class="q-r-r-num">
                      <div class="replyNum">
                        <span class="r-b-num">{{ item.answerNumber }}</span>
                        <p class="hLh20">
                          <span class="c-999 f-fA">回答数</span>
                        </p>
                      </div>
                    </aside>
                    <h4 class="hLh30 txtOf">
                      <em class="icon16 q-tw">&nbsp;</em>
                      <a
                        :href="'/qa/' + item.id"
                        title=""
                        class="fsize14 c-333 ml5"
                        >{{ item.title }}</a
                      >
                    </h4>
                  </li>
                </ul>
              </div>
            </section>
            <!-- /热门问答排行 -->
          </div>
        </aside>
        <div class="clear"></div>
      </section>
    </section>
    <!-- /提问题 结束 -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      raiser: "学员1",
      title: "我的MYSQL日志学习心得,给大家分享",
      content:
        "Premiere视频教学视频资料,有哪位大神可以分享下吗,膜拜膜拜膜拜膜拜膜拜膜拜膜拜膜拜膜拜膜拜膜拜膜拜膜拜",
      date: "2021-09-10 10:31",
      type: "MySql",
      userImg: require("../../assets/photo/customer/02.jpg"),
      hotQuestionList: [
        { id: 1, title: "photoshop怎么抠图 ,能详细点吗", answerNumber: 3 },
        { id: 2, title: "photoshop怎么抠图 ,能详细点吗", answerNumber: 2 },
        { id: 3, title: "photoshop怎么抠图 ,能详细点吗", answerNumber: 1 },
        { id: 4, title: "photoshop怎么抠图 ,能详细点吗", answerNumber: 2 },
        { id: 5, title: "photoshop怎么抠图 ,能详细点吗", answerNumber: 3 },
        { id: 6, title: "photoshop怎么抠图 ,能详细点吗", answerNumber: 4 },
      ],
      questionTypes: [
        { id: 0, type: "全部" },
        { id: 1, type: "Java" },
        { id: 2, type: "Python" },
        { id: 3, type: "MySql" },
        { id: 4, type: "C++" },
        { id: 5, type: "Android" },
        { id: 6, type: "JavaScript" },
        { id: 7, type: "Vue" },
        { id: 8, type: "SPringboot" },
      ],
    };
  },

  components: {},

  computed: {},

  mounted() {},

  methods: {},
};
</script>
<style scoped>
</style>