<template>
  <div v-if="details[0]">
    <!-- 返回键  分享键 -->
    <!-- 6.16 -->
    <div>
      <van-nav-bar
        title=""
        left-text="返回"
        left-arrow
        @click-left="$router.push('/home/index')"
      >
        <template #right>
          <van-cell
            title=""
            @click="showShare = true"
            style="height: 46px; width: 200px"
          >
            <van-icon name="share" size="18" style="margin-right: 15px" />
          </van-cell>
          <van-share-sheet
            v-model:show="showShare"
            title="将课程分享至"
            :options="options"
            @select="onSelect"
          />
        </template>
      </van-nav-bar>
    </div>
    <!-- 课程详情 -->
    <div style="width: 100%">
      <video
        id="video"
        style="height: 220.42px"
        src="../assets/donghua/shili.mp4"
        controls
        width="100%"
        :poster="`/Img/${details[0].index_img}.png`"
      ></video>
    </div>
    <div id="kname" class="clear">
      <div id="kname1">
        <span class="kname1_1">免费</span>
        <span class="kname1_2">8125人最近报名</span>
      </div>
      <h3 class="kname1_3">{{ details[0].class_title }}</h3>
      <div class="kname1_4">
        <img src="../assets/img/alogo.png" alt="" class="kname1_5" />
        <a href=""><span class="kname1_6">好评帮，直播电商第4名</span></a>
      </div>
    </div>
    <!-- 腾讯课堂详情页 6.10 19 -->
    <div class="test">
      <van-tabs v-model="active">
        <van-tab title="介绍">
          <div id="mt1" class="clear">
            <div class="mt1_1">
              <img class="mt1_1_1" src="../assets/img/wenjianjia.jpg" alt="" />
              <div>
                <div><span class="mt1_1_1_1">免费领取资料</span></div>
                <div><span class="mt1_1_1_2">联系老师领取干货资料</span></div>
              </div>
            </div>
          </div>
          <div it="mt1_2">
            <div style="padding: 0 16px">
              <h3 class="mt1_21">讲师介绍</h3>
            </div>
            <div id="mt1_2_1" class="clear">
              <img
                :src="`/Img/${details[0].teacher_head}.jpg`"
                alt=""
                class="mt1_2_1_1"
              />
              <div>
                <p class="mt1_2_1_1_1">{{ details[0].teacher }}</p>
                <span class="mt1_2_1_1_2">{{
                  details[0].teacher_introduce
                }}</span>
              </div>
            </div>
          </div>
          <div style="padding: 1.15rem">
            <div>
              <h4 style="text-align: center; color: #666c80">课程详情</h4>
              <div>
                <img
                  :src="`/Img/${details[0].detail_img}.jpg`"
                  alt=""
                  style="width: 100%"
                />
              </div>
            </div>
          </div>
        </van-tab>
        <van-tab title="目录">
          <h3 style="padding: 8px 16px; font-size: 1.14rem">课程目录</h3>
          <div class="mt2_1">
            <van-collapse v-model="activeNames">
              <van-collapse-item title="第一节" name="1"
                ><div>1.vue指令</div></van-collapse-item
              >
              <van-collapse-item title="第二节" name="2"
                ><div>2.vue生命周期、组件</div></van-collapse-item
              >
              <van-collapse-item title="第三节" name="3"
                ><div>
                  3.vue自定义指令、计算属性、常用属性方法
                </div></van-collapse-item
              >
              <van-collapse-item title="第四节" name="4"
                ><div>4、vue-router\vue-cli</div></van-collapse-item
              >
              <van-collapse-item title="第五节" name="5"
                ><div>5、Vue项目实战1</div></van-collapse-item
              >
              <van-collapse-item title="第六节" name="6"
                ><div>6、Vue项目实战2</div></van-collapse-item
              >
              <van-collapse-item title="第七节" name="7"
                ><div>7、H5购物车详细解析vuex</div></van-collapse-item
              >
              <van-collapse-item title="第八节" name="8"
                ><div>8、Vue源码解析</div></van-collapse-item
              >
              <van-collapse-item title="第九节" name="9"
                ><div>9、Vue+echarts实现疫情地图</div>
                <div>9.1、Vue+echarts实现疫情地图</div>
                </van-collapse-item
              >
              <van-collapse-item title="第十节" name="10"
                ><div>10、Vue自定义指令实现图片懒加载</div></van-collapse-item
              >
            </van-collapse>
            <div class="mt2_2">
              <p style="font-size: 0.8rem; color: #3e414d">
                APP内学习，流畅又清晰
              </p>
            </div>
          </div>
        </van-tab>
        <van-tab title="评价">
          <div>
            <div class="clear" id="mt3">
              <div>
                <h3 style="font-size: 1.14rem">学员评价(6)</h3>
              </div>
              <div>
                <a href="" style="font-size: 0.8rem; color: #3e414d"
                  >查看全部</a
                >
              </div>
            </div>

            <div>
              <div class="clear" id="mt3_1">
                <!-- 用户头像 -->
                <div>
                  <img
                    src="../assets/img/userlog1.jpg"
                    alt=""
                    style="width: 32px; height: 32px"
                  />
                </div>
                <!-- 昵称|时间 -->
                <div style="font-size: 1rem; line-height: 1.5rem">
                  <p>***三</p>
                  <p style="color: gray">
                    8个月前|已上课3小时20分钟评论 <span>五星好评</span>
                  </p>
                </div>
              </div>
              <div id="mt3_1_1">
                <p style="padding: 0; margin: 0">
                  很好 很喜欢老师的课程 作为一个小白 虽然不是老师的学生
                  但是老师课后也会帮助我 帮我解决我的困惑 谢谢老师
                </p>
              </div>
            </div>

            <div>
              <div class="clear" id="mt3_1">
                <!-- 用户头像 -->
                <div>
                  <img
                    src="../assets/img/userlog1.jpg"
                    alt=""
                    style="width: 32px; height: 32px"
                  />
                </div>
                <!-- 昵称|时间 -->
                <div style="font-size: 1rem; line-height: 1.5rem">
                  <p>***三</p>
                  <p style="color: gray">
                    8个月前|已上课3小时20分钟评论 <span>五星好评</span>
                  </p>
                </div>
              </div>
              <div id="mt3_1_1">
                <p style="padding: 0; margin: 0">
                  很好 很喜欢老师的课程 作为一个小白 虽然不是老师的学生
                  但是老师课后也会帮助我 帮我解决我的困惑 谢谢老师
                </p>
              </div>
            </div>

            <div>
              <div class="clear" id="mt3_1">
                <!-- 用户头像 -->
                <div>
                  <img
                    src="../assets/img/userlog1.jpg"
                    alt=""
                    style="width: 32px; height: 32px"
                  />
                </div>
                <!-- 昵称|时间 -->
                <div style="font-size: 1rem; line-height: 1.5rem">
                  <p>***三</p>
                  <p style="color: gray">
                    8个月前|已上课3小时20分钟评论 <span>五星好评</span>
                  </p>
                </div>
              </div>
              <div id="mt3_1_1">
                <p style="padding: 0; margin: 0">
                  很好 很喜欢老师的课程 作为一个小白 虽然不是老师的学生
                  但是老师课后也会帮助我 帮我解决我的困惑 谢谢老师
                </p>
              </div>
            </div>
            <div>
              <div class="clear" id="mt3_1">
                <!-- 用户头像 -->
                <div>
                  <img
                    src="../assets/img/userlog1.jpg"
                    alt=""
                    style="width: 32px; height: 32px"
                  />
                </div>
                <!-- 昵称|时间 -->
                <div style="font-size: 1rem; line-height: 1.5rem">
                  <p>***三</p>
                  <p style="color: gray">
                    8个月前|已上课3小时20分钟评论 <span>五星好评</span>
                  </p>
                </div>
              </div>
              <div id="mt3_1_1">
                <p style="padding: 0; margin: 0">
                  很好 很喜欢老师的课程 作为一个小白 虽然不是老师的学生
                  但是老师课后也会帮助我 帮我解决我的困惑 谢谢老师
                </p>
              </div>
            </div>
            <div>
              <div class="clear" id="mt3_1">
                <!-- 用户头像 -->
                <div>
                  <img
                    src="../assets/img/userlog1.jpg"
                    alt=""
                    style="width: 32px; height: 32px"
                  />
                </div>
                <!-- 昵称|时间 -->
                <div style="font-size: 1rem; line-height: 1.5rem">
                  <p>***三</p>
                  <p style="color: gray">
                    8个月前|已上课3小时20分钟评论 <span>五星好评</span>
                  </p>
                </div>
              </div>
              <div id="mt3_1_1">
                <p style="padding: 0; margin: 0">
                  很好 很喜欢老师的课程 作为一个小白 虽然不是老师的学生
                  但是老师课后也会帮助我 帮我解决我的困惑 谢谢老师
                </p>
              </div>
            </div>
          </div>
        </van-tab>
        <van-tab title="推荐">
          <h3 style="padding: 12px 16px; font-size: 1.14286rem; color: #3c464f">
            授课机构
          </h3>
          <div id="mt4" class="clear">
            <img src="../assets/img/teacther.jpg" alt="" class="mt4_1" />
            <div style="padding: 12px 0px">
              <p>
                <span class="mt4_1_1">视商研习社</span>
              </p>
              <ul id="mt4_1_1_1" class="clear">
                <li>好评度100%</li>
                <li>·</li>
                <li>课程数5</li>
                <li>·</li>
                <li>学生数8571</li>
              </ul>
            </div>
          </div>
          <div
            style="display: flex; padding: 12px 16px; align-items: center"
            class="clear"
          >
            <img
              src="../assets/img/qqlog.jpg"
              alt=""
              style="width: 20px; height: 20px"
            />
            <div class="is-qq">福利群</div>
            <div class="is-qq_1">定期发放干货资料，优惠福利</div>
            <div><i></i></div>
          </div>

          <h3
            style="
              padding: 0 16px;
              font-size: 1.14286rem;
              display: flex;
              justify-content: space-between;
              color: #3e414d;
            "
          >
            关联的付费课程
            <div>
              <img src="../assets/img/tclogo.png" alt="" />
              <span
                style="display: inline-block; font-size: 0.8rem; color: #3e414d"
              >
                <i></i>
                获取选课建议
              </span>
            </div>
          </h3>

          <div>
            <div id="mt4_2">
              <div style="margin-right: 10px">
                <img
                  src="../assets/img/dyjj01.jpg"
                  alt=""
                  style="height: 70px; width: 124px"
                />
              </div>
              <div>
                <div>
                  <div>
                    <h5 style="margin: 5px 0">
                      抖音vlog短视频自媒体制作引流运营赚钱盈利全攻略实战福利课教程
                    </h5>
                  </div>
                  <div style="margin: 5px 0">
                    <span id="mt4_3_1">￥98</span>
                    <span style="font-size: 0.8rem">6人最近报名</span>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <div>
            <h3 style="padding: 0 16px; font-size: 1.14286rem">
              <span>机构课程推荐</span>
            </h3>
            <div id="mt4_3">
              <div style="margin-right: 10px">
                <img
                  src="../assets/img/dyjj01.jpg"
                  alt=""
                  style="height: 70px; width: 124px"
                />
              </div>
              <div>
                <div>
                  <div>
                    <h5 style="margin: 5px 0">
                      抖音vlog短视频自媒体制作引流运营赚钱盈利全攻略实战福利课教程
                    </h5>
                  </div>
                  <div style="margin: 5px 0">
                    <span id="mt4_3_1">免费</span>
                    <span style="font-size: 0.8rem">6人最近报名</span>
                  </div>
                </div>
              </div>
            </div>

            <div id="mt4_3">
              <div style="margin-right: 10px">
                <img
                  src="../assets/img/dyjj01.jpg"
                  alt=""
                  style="height: 70px; width: 124px"
                />
              </div>
              <div>
                <div>
                  <div>
                    <h5 style="margin: 5px 0">
                      抖音vlog短视频自媒体制作引流运营赚钱盈利全攻略实战福利课教程
                    </h5>
                  </div>
                  <div style="margin: 5px 0">
                    <span id="mt4_3_1">免费</span>
                    <span style="font-size: 0.8rem">6人最近报名</span>
                  </div>
                </div>
              </div>
            </div>

            <div id="mt4_3">
              <div style="margin-right: 10px">
                <img
                  src="../assets/img/dyjj01.jpg"
                  alt=""
                  style="height: 70px; width: 124px"
                />
              </div>
              <div>
                <div>
                  <div>
                    <h5 style="margin: 5px 0">
                      抖音vlog短视频自媒体制作引流运营赚钱盈利全攻略实战福利课教程
                    </h5>
                  </div>
                  <div style="margin: 5px 0">
                    <span id="mt4_3_1">免费</span>
                    <span style="font-size: 0.8rem">6人最近报名</span>
                  </div>
                </div>
              </div>
            </div>

            <div id="mt4_3">
              <div style="margin-right: 10px">
                <img
                  src="../assets/img/dyjj01.jpg"
                  alt=""
                  style="height: 70px; width: 124px"
                />
              </div>
              <div>
                <div>
                  <div>
                    <h5 style="margin: 5px 0">
                      抖音vlog短视频自媒体制作引流运营赚钱盈利全攻略实战福利课教程
                    </h5>
                  </div>
                  <div style="margin: 5px 0">
                    <span id="mt4_3_1">免费</span>
                    <span style="font-size: 0.8rem">6人最近报名</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </van-tab>
      </van-tabs>
    </div>
  </div>
</template>

<script>
import { Toast } from "vant";

export default {
  props: ["cid"],
  mounted() {
    this.axios.get("/items/details?cid=" + this.cid).then((res) => {
      console.log(res);
      this.details = res.data.result;
    });
  },
  data() {
    return {
      activeNames: ["0"],
      active: 0,
      selected: 1,
      details: [],
      showShare: false,
      options: [
        { name: "微信", icon: "wechat" },
        { name: "微博", icon: "weibo" },
        { name: "复制链接", icon: "link" },
        { name: "分享海报", icon: "poster" },
        { name: "二维码", icon: "qrcode" },
      ],
    };
  },
  methods: {
    onSelect(option) {
      Toast(option.name);
      this.showShare = false;
    },
  },
};
</script>

<style lang="scss" >
div {
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
}
.clear:after {
  content: “”;
  display: block;
  clear: both;
}
#kname {
  padding: 2px 16px;
}
#kname1 {
  display: flex;
  justify-content: space-between;
  margin-top: 12px;
}
.kname1_1 {
  color: #ff7a38;
  font-size: 1.14rem;
}
.kname1_2 {
  color: gray;
  font-size: 0.8rem;
}
.kname1_3 {
  margin-top: 0;
  color: #192630;
}
.kname1_4 {
  // margin-top: 0;
  padding: 12px 0;
  margin-top: 12px;
}
.kname1_5 {
  height: 1.14rem;
  width: 1.14rem;
  margin-right: 4px;
}

.kname1_6 {
  font-size: 0.86rem;
  color: gray;
  line-height: 1.14rem;
}
#mt1 {
  height: 115px;
  width: 100%;
  padding: 16px;
  display: flex;
  align-items: center;
}
.mt1_1 {
  display: flex;
}
#mt1 .mt1_1 .mt1_1_1 {
  width: 36px;
  height: 36px;
  margin-right: 10px;
}
.mt1_1_1_1 {
  font-size: 1rem;
  color: #3e414d;
}
.mt1_1_1_2 {
  font-size: 0.8rem;
  color: #666c80;
}
#mt1_2 {
  height: 136px;
  padding: 0;
  width: 100%;
}
.mt1_21 {
  color: #3c464f;
  font-size: 1.21rem;
}
#mt1_2_1 {
  padding: 0 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 16px;
}
.mt1_2_1_1 {
  height: 2.5rem;
  width: 2.5rem;
  margin-right: 10px;
  border-radius: 50%;
}
.mt1_2_1_1_1 {
  font-size: 0.8rem;
  margin: 2px 0;
  color: #3e414d;
}
.mt1_2_1_1_2 {
  font-size: 0.6rem;
  margin: 2px 0;
  color: #666c80;
}
.mt2_1 {
  max-height: 520px;
  margin-bottom: 30px;
  padding: 4px 16px;
  color: gray;
  margin-left: 8px;
}
.mt2_1_1 {
  padding: 4px 0;
}
.mt2_2 {
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 600;
  color: black;
}
#mt3 {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 16px;
}
#mt3_1 {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0px 16px;
}
#mt3_1_1 {
  padding: 0 16px;
  margin: 0 0 0 48px;
}
#mt4 {
  display: flex;
  align-items: center;
  padding: 0 16px;
}
.mt4_1 {
  width: 36px;
  height: 36px;
  margin-right: 10px;
}
.mt4_1_1 {
  font-size: 1rem;
  margin: 2px 1px;
}
#mt4_1_1_1 {
  display: flex;
  font-size: 0.75rem;
  margin: 2px 1px;
}
.is-qq {
  font-size: 1rem;
  margin: 0px 8px;
}
.is-qq_1 {
  font-size: 0.8rem;
}
#mt4_2 {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 16px;
}
#mt4_3 {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 16px;
}
#mt4_3_1 {
  font-size: 0.8rem;
  margin-right: 6px;
  color: #ff7a38;
}
.van-tabs__line {
  background-color: #1989fa;
  width: 20px;
  z-index: 0;
}
</style>