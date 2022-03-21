<template>
  <div class="bg-fa of">
    <section class="container">
      <section class="i-question">
        <div class="fl col-7">
          <section class="mr30 pt10">
            <section class="c-infor-tabTitle c-tab-title">
              <a
                href="javascript: void(0)"
                title="全部问答"
                onclick="submitForm(0,'type')"
                class="current"
                >全部问答</a
              >
            </section>
            <div class="js-wrap">
              <section class="fl">
                <ol class="js-tap clearfix">
                  <li class="current bg-orange">
                    <a
                      onclick="submitForm('addTime','order')"
                      href="javascript:void(0)"
                      title="最新"
                      >最新</a
                    >
                  </li>
                  <li>
                    <a
                      onclick="submitForm('replycount','order')"
                      href="javascript:void(0)"
                      title="热门"
                      >热门</a
                    >
                  </li>
                  <li>
                    <a
                      onclick="submitForm('status0','order')"
                      href="javascript:void(0)"
                      title="等待回答"
                      >等待回答</a
                    >
                  </li>
                </ol>
              </section>
            </div>
            <div class="q-list">
              <section class="q-all-list">
                <ul>
                  <li v-for="item in questionList" :key="item.id">
                    <aside class="q-head-pic">
                      <img :src="item.userImg" alt="" />
                      <p class="hLh30 txtOf">
                        <span class="c-999"> item.userName</span>
                      </p>
                    </aside>
                    <section class="q-txt-box">
                      <a
                        class="replyBrowseNum"
                        :href="'/qa/' + item.id"
                        title=""
                      >
                        <div class="replyNum">
                          <span class="r-b-num">{{ item.answerNumber }}</span>
                          <p class="hLh30">
                            <span class="c-999 f-fA">回答数</span>
                          </p>
                        </div>
                        <div class="browseNum">
                          <span class="r-b-num">{{ item.lookNumber }}</span>
                          <p class="hLh30">
                            <span class="c-999 f-fA">浏览数</span>
                          </p>
                        </div>
                      </a>
                      <h3 class="hLh30 txtOf">
                        <em class="icon16 q-tw">&nbsp;</em>
                        <a
                          :href="'/qa/' + item.id"
                          title=""
                          class="fsize16 c-333 vam"
                          >{{ item.title }}</a
                        >
                      </h3>
                      <h3 class="hLh30 txtOf mt5" v-if="item.answerNumber != 0">
                        <em class="icon16 q-hd">&nbsp;</em>
                        <span class="fsize12 c-999 vam">
                          <tt class="c-green f-fM mr5">[最佳回答]</tt>
                          {{ item.answer }}</span
                        >
                        <!-- 采纳最佳显示最佳答案内容 -->
                      </h3>
                      <h3 class="hLh30 txtOf mt5" v-else>
                        <em class="icon16 q-hd">&nbsp;</em>
                        <span class="fsize12 c-999 vam"
                          >哈~~~ 此问题大家还有苦思冥想中...</span
                        >
                        <!-- 没有回答时的内容 -->
                      </h3>
                      <div class="mt15">
                        <span class="c-ccc fl vam">2015-09-10 10:31</span>
                        <section class="fl ml20 pt10">
                          <div class="taglist clearfix">
                            <a
                              title="Premiere"
                              data-id="5"
                              onclick="submitForm('5','questionsTagId')"
                              class="list-tag"
                              href="javascript:;"
                              >{{ item.type }}</a
                            >
                          </div>
                        </section>
                        <div class="clear"></div>
                      </div>
                    </section>
                  </li>
                </ul>
              </section>

              <!-- 公共分页 开始 -->
              <div>
                <div class="paging">
                  <a class="undisable" title="">首</a>
                  <a id="backpage" class="undisable" href="#" title="">&lt;</a>
                  <a href="#" title="" class="current undisable">1</a>
                  <a id="nextpage" href="#" title="">&gt;</a>
                  <a href="#" title="">末</a>
                  <div class="clear"></div>
                </div>
              </div>
              <!-- 公共分页 结束 -->
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
      questionList: [
        {
          id: 1,
          userImg: require("../../assets/photo/customer/01.jpg"),
          userName: "学员1",
          answerNumber: 3,
          lookNumber: 999,
          answer:
            "premiere是一款常用的视频编辑软件，由Adobe公司推出。现在常用的有CS4CS5CS6等版本。是一款编辑画面质量比较好的软件，有较好的兼容性，且可以与adobe公司推出的其他软件相互协作。目前这款软件广泛应用于广告制作和电视节目制作中。其最新版本为Adobe Premiere Pro CC。",
          title: "我的MYSQL日志学习心得,给大家分享",
          type: "MySQL",
        },
        {
          id: 2,
          userImg: require("../../assets/photo/customer/02.jpg"),
          userName: "学员2",
          answerNumber: 0,
          lookNumber: 999,
          answer:
            "premiere是一款常用的视频编辑软件，由Adobe公司推出。现在常用的有CS4CS5CS6等版本。是一款编辑画面质量比较好的软件，有较好的兼容性，且可以与adobe公司推出的其他软件相互协作。目前这款软件广泛应用于广告制作和电视节目制作中。其最新版本为Adobe Premiere Pro CC。",
          title: "我的MYSQL日志学习心得,给大家分享",
          type: "MySQL",
        },
        {
          id: 3,
          userImg: require("../../assets/photo/customer/03.jpg"),
          userName: "学员3",
          answerNumber: 1,
          lookNumber: 998,
          answer:
            "premiere是一款常用的视频编辑软件，由Adobe公司推出。现在常用的有CS4CS5CS6等版本。是一款编辑画面质量比较好的软件，有较好的兼容性，且可以与adobe公司推出的其他软件相互协作。目前这款软件广泛应用于广告制作和电视节目制作中。其最新版本为Adobe Premiere Pro CC。",
          title: "我的MYSQL日志学习心得,给大家分享",
          type: "MySQL",
        },
        {
          id: 4,
          userImg: require("../../assets/photo/customer/02.jpg"),
          userName: "学员4",
          answerNumber: 2,
          lookNumber: 888,
          answer:
            "premiere是一款常用的视频编辑软件，由Adobe公司推出。现在常用的有CS4CS5CS6等版本。是一款编辑画面质量比较好的软件，有较好的兼容性，且可以与adobe公司推出的其他软件相互协作。目前这款软件广泛应用于广告制作和电视节目制作中。其最新版本为Adobe Premiere Pro CC。",
          title: "我的MYSQL日志学习心得,给大家分享",
          type: "MySQL",
        },
        {
          id: 5,
          userImg: require("../../assets/photo/customer/02.jpg"),
          userName: "学员5",
          answerNumber: 0,
          lookNumber: 999,
          answer:
            "premiere是一款常用的视频编辑软件，由Adobe公司推出。现在常用的有CS4CS5CS6等版本。是一款编辑画面质量比较好的软件，有较好的兼容性，且可以与adobe公司推出的其他软件相互协作。目前这款软件广泛应用于广告制作和电视节目制作中。其最新版本为Adobe Premiere Pro CC。",
          title: "我的MYSQL日志学习心得,给大家分享",
          type: "MySQL",
        },
        {
          id: 6,
          userImg: require("../../assets/photo/customer/02.jpg"),
          userName: "学员6",
          answerNumber: 3,
          lookNumber: 999,
          answer:
            "premiere是一款常用的视频编辑软件，由Adobe公司推出。现在常用的有CS4CS5CS6等版本。是一款编辑画面质量比较好的软件，有较好的兼容性，且可以与adobe公司推出的其他软件相互协作。目前这款软件广泛应用于广告制作和电视节目制作中。其最新版本为Adobe Premiere Pro CC。",
          title: "我的MYSQL日志学习心得,给大家分享",
          type: "MySQL",
        },
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
      hotQuestionList: [
        { id: 1, title: "photoshop怎么抠图 ,能详细点吗", answerNumber: 3 },
        { id: 2, title: "photoshop怎么抠图 ,能详细点吗", answerNumber: 2 },
        { id: 3, title: "photoshop怎么抠图 ,能详细点吗", answerNumber: 1 },
        { id: 4, title: "photoshop怎么抠图 ,能详细点吗", answerNumber: 2 },
        { id: 5, title: "photoshop怎么抠图 ,能详细点吗", answerNumber: 3 },
        { id: 6, title: "photoshop怎么抠图 ,能详细点吗", answerNumber: 4 },
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