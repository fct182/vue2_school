<template>
  <div class="home-view">
    <!-- 顶部导航 -->
    <div class="wp-wrapper top-header">
      <div class="wp-inner clearfix">
        <!--副导航开始-->
        <div class="top-nav-panel" frag="左侧导航">
          <div class="" frag="左侧导航">
            <ul class="wp-menu clearfix">
              <li
                v-for="(item, index) in leftNavData"
                :key="index"
                class="menu-item"
              >
                <a class="menu-link">{{ item }}</a>
              </li>
            </ul>
          </div>
        </div>
        <!--//副导航结束-->
        <div class="clearfix right-nav-search">
          <!--搜索开始-->
          <div class="panel-3" frag="搜索">
            <a href="javascript:void(0)" id="myBtn"></a>
          </div>
          <!--//搜索结束-->
          <!--右侧导航开始-->
          <div class="lang-panel" frag="右侧导航">
            <div class="wp-window lang-window" frag="右侧导航">
              <ul class="wp-menu clearfix">
                <li
                  v-for="(item, index) in rightNavData"
                  :key="index"
                  class="menu-item"
                >
                  <a class="menu-link">{{ item }}</a>
                </li>
              </ul>
            </div>
          </div>
          <!--//右侧导航结束-->
        </div>
      </div>
    </div>
    <!-- 头部区域 -->
    <header class="wp-wrapper wp-header">
      <!-- 图标 -->
      <div class="top-nav">
        <div class="wp-inner clearfix">
          <!--logo开始-->
          <div class="logo-panel" frag="学校logo">
            <div class="wp-window logo-window" frag="学校logo">
              <img class="site-logo" src="../assets/img/logo-scdx.png" />
            </div>
          </div>
          <!--//logo结束-->
        </div>
      </div>
      <!-- 主要导航 -->
      <div class="wp-wrapper" id="naver">
        <div class="wp-inner">
          <div class="main-nav-panel" frag="主要导航">
            <div class="" frag="主要导航">
              <ul class="clearfix" id="nav">
                <li
                  v-for="(item, index) in mainNavData"
                  :key="index"
                  class="mainlevel"
                >
                  <a>{{ item }}</a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
      <!-- 轮播图 -->
      <div class="wp-wrapper wp-focus">
        <div class="wp-inner">
          <el-carousel height="380px" trigger="click">
            <el-carousel-item
              v-for="(item, index) in carouselData"
              :key="index"
            >
              <img :src="item" :alt="`轮播图-${index}`" />
            </el-carousel-item>
          </el-carousel>
        </div>
      </div>
    </header>
    <!-- 主体内容-1 -->
    <div class="wp-wrapper wp-container">
      <div class="wp-inner clearfix">
        <div class="content1 clearfix">
          <div class="cbox-right">
            <!-- 新闻头 -->
            <div class="wp-post">
              <div class="post-head">
                <div class="head-bar">
                  <h3 class="post-title">
                    <span><a>综合新闻</a></span>
                  </h3>
                  <div class="post-more">
                    <a>&gt;&gt;进入新闻网</a>
                  </div>
                </div>
              </div>
            </div>
            <!-- 新闻主体 -->
            <div class="z_news clearfix">
              <!-- 左侧图片 -->
              <div class="z_news_l">
                <ul class="con_news_pic">
                  <li class="news-item clearfix">
                    <div class="news_pic">
                      <img src="../assets/img/main-news.jpg" width="640" />
                    </div>
                    <div class="news_tit">
                      <div style="font-family: 宋体">
                        <a
                          >“品传统经典
                          承千年精粹”：XX大学首届学生传统文化节启幕</a
                        >
                      </div>
                      <div class="news_pres" style="display: none">04.11</div>
                    </div>
                  </li>
                </ul>
              </div>
              <!-- 右侧新闻列表 -->
              <div class="z_news_m">
                <div class="con_news_nav" frag="右侧列表">
                  <ul class="post-news">
                    <li
                      v-for="(item, index) in newsList"
                      :key="index"
                      class="news-item clearfix"
                    >
                      <span class="meta-title"
                        ><a>{{ item.text }}</a></span
                      ><span class="meta-time">{{ item.time }}</span>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- 底部内容 -->
    <div class="wp-wrapper wp-container3">
      <div class="wp-inner clearfix">
        <!-- 底部左侧导航 -->
        <div class="left_frame" frag="底部左侧导航">
          <div id="wp_nav_w50">
            <ul class="wp_nav" style="height: auto">
              <li
                v-for="(item, index) in bottomLeftNav"
                :key="index"
                class="nav-item"
              >
                <a :title="item"
                  ><span class="item-name">{{ item }}</span></a
                >
              </li>
            </ul>
          </div>
        </div>
        <div class="right_frame clearfix">
          <!-- 底部右侧微博、微信、易班 -->
          <ul class="share clearfix list-paddingleft-2">
            <li
              v-for="(item, index) in bottomRightShare"
              :class="item"
              :key="index"
            >
              <a href=""></a>
            </li>
          </ul>
          <!-- 底部右侧导航 -->
          <div class="bottom_link" frag="底部右侧导航">
            <ul class="wp_nav">
              <template v-for="(item, index) in bottomRightNav">
                <li
                  class="nav-item"
                  :key="index"
                  :class="{ 'first-li': index === 0 }"
                >
                  <a
                    ><span class="item-name">{{ item }}</span></a
                  >
                </li>
              </template>
            </ul>
          </div>
          <!-- 地址信息 -->
          <div class="bottom_addr">
            <p>地址：中国·四川·成都市 XX大学(610039)</p>
            <p>电话：(028)87720037 传真：(028)87720200</p>
            <p>招生咨询：028-87720918 就业咨询：028-87722647</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// 引入轮播图
import carousel_0 from '../assets/img/carousel_00.jpg';
import carousel_1 from '../assets/img/carousel_01.jpg';
import carousel_2 from '../assets/img/carousel_02.jpg';
import carousel_3 from '../assets/img/carousel_03.jpg';
export default {
  name: 'HomeView',
  data() {
    return {
      // 页面顶部左侧的导航显示文本
      leftNavData: [
        '在校学生',
        '教职员工',
        '校友',
        '未来学生',
        '学生家长',
        '公众访客'
      ],
      // 页面顶部右侧的导航显示文本
      rightNavData: [
        'OA',
        '学校易班',
        '教务系统',
        '教师邮件',
        '学生邮件',
        '办事大厅',
        '图书馆'
      ],
      // 轮播图上的导航显示文本
      mainNavData: [
        '学校概况',
        '机构设置',
        '人才培养',
        '科学研究',
        '招生就业',
        '合作交流',
        '公共服务',
        '人才招聘'
      ],
      // 轮播图
      carouselData: [carousel_0, carousel_1, carousel_2, carousel_3],
      // 新闻列表
      newsList: [
        {
          text: '学校召开党委常委会（扩大）会议专题学习研讨习近平总书记关于教育的重要论述',
          time: '2023-05-13'
        },
        {
          text: '四川省体育局党组书记、局长罗冬灵一行来校调研',
          time: '2023-05-13'
        },
        {
          text: 'XX大学与宜宾丰川动力科技公司举行校企合作工作推进会',
          time: '2023-05-12'
        },
        {
          text: '我校师生参加“2023中国·浑源首届“恒山黄芪”新品研发大赛暨精深加工论坛',
          time: '2023-05-12'
        },
        { text: 'XX大学教师赴雷波县开展文化帮扶', time: '2023-05-12' },
        {
          text: 'XX大学《现代工程项目管理》研究生课程上线新华网“新华思政”平台',
          time: '2023-05-11'
        },
        {
          text: '眉山市应急管理综合行政执法人员入职暨能力提升培训班在XX大学举行',
          time: '2023-05-11'
        },
        {
          text: '美术与设计学院赴南充开展 “田间插秧践初心忆苦思甜促振兴” 主题党日活动',
          time: '2023-05-09'
        }
      ],
      // 底部左侧导航
      bottomLeftNav: [
        'OA',
        '图书馆',
        '课程中心',
        '教务系统',
        '本科招生',
        '诚聘英才',
        '网络理政',
        '信息门户',
        '站群管理',
        '教师主页',
        '政府采购机票网站'
      ],
      // 底部右侧-微博、微信、易班
      bottomRightShare: ['add-weixin', 'add-tqq', 'add-weibo'],
      // 底部右侧导航
      bottomRightNav: ['书记信箱', '校长信箱', '友情链接', '联系我们']
    };
  }
};
</script>

<style lang="scss">
.home-view {
  // 公有样式--内容居中
  .wp-wrapper {
    width: 100%;
    .wp-inner {
      margin: 0 auto;
      width: auto;
      max-width: 1200px;
    }
  }
  // 公有样式--清除浮动
  .clearfix {
    display: block;
    &::after {
      clear: both;
      display: block;
      visibility: hidden;
      height: 0;
      content: '.';
    }
  }
  // a超链接均设鼠标样式为-pointer
  a {
    cursor: pointer;
  }

  // 顶部导航
  .top-header {
    background: #004c7e;
    .top-nav-panel {
      float: left;
      .wp-menu {
        float: right;
        white-space: nowrap;
        .menu-item {
          // display: inline-block;
          float: left;
          .menu-link {
            display: inline-block;
            padding: 0 14px;
            height: 36px;
            background: url('../assets/img/lead_vo.png') right center no-repeat;
            color: #cbd6e3;
            font-size: 13px;
            line-height: 36px;
          }
        }
      }
    }
    .right-nav-search {
      width: 50%;
      float: right;
      .panel-3 {
        position: relative;
        float: right;
        margin-right: 10px;
        #myBtn {
          display: block;
          padding-top: 11px;
          width: 24px;
          height: 24px;
          background: url('../assets/img/search.png') center center no-repeat;
        }
      }
      .lang-panel {
        float: left;
        margin-right: 10px;
        .lang-window {
          padding: 0;
          .wp-menu {
            float: right;
            .menu-item {
              float: left;
              .menu-link {
                display: inline-block;
                margin: 0 6px;
                height: 36px;
                color: #ebb428;
                font-size: 14px;
                line-height: 36px;
              }
            }
          }
        }
      }
    }
  }

  // 头部区域
  .wp-header {
    position: relative;
    background: #005691;
    .wp-inner {
      position: relative;
    }
    .top-nav {
      padding: 14px 0;
      .wp-inner {
        background: url('../assets/img/head_bg.png') right 6px no-repeat;
        .logo-panel {
          float: left;
          .logo-window {
            padding: 18px 0;
            margin-left: 10px;
            img {
              vertical-align: middle;
            }
          }
        }
      }
    }
    #naver {
      position: relative;
      z-index: 10;
      background: #0e6bc2;
      .wp-inner {
        width: 100%;
      }
      .main-nav-panel {
        height: 50px;
        #nav {
          display: block;
          .mainlevel {
            float: left;
            a {
              display: block;
              padding: 0 40px;
              color: #fff;
              text-decoration: none;
              font-size: 16px;
              line-height: 50px;
              &:hover {
                background: #005691;
                color: #fff;
                text-decoration: none;
              }
            }
          }
        }
      }
    }
    .wp-focus {
      position: relative;
      z-index: 9;
      background-color: #ececec;
      img {
        width: 100%;
        height: 100%;
        border: 0;
        vertical-align: top;
      }
      .el-carousel__arrow {
        background-color: rgba($color: #222, $alpha: 0.5);
      }
    }
  }

  // 主体内容-1
  .wp-container {
    .wp-inner {
      padding: 15px 0 40px 0;
      .content1 {
        .cbox-right {
          float: left;
          margin-right: 0;
          width: 100%;
          .wp-post {
            .post-head {
              height: 52px;
              border-bottom: 2px solid #004e8a;
              .head-bar {
                position: relative;
                .post-title {
                  display: inline-block;
                  height: 50px;
                  font-weight: 400;
                  font-size: 20px;
                  line-height: 50px;
                }
                .post-more {
                  position: absolute;
                  top: 50%;
                  right: 0;
                  margin-top: -10px;
                  height: 20px;
                  line-height: 20px;
                }
              }
            }
          }
          .z_news {
            .z_news_l {
              float: left;
              margin-top: 10px;
              width: 43.75%;
              .con_news_pic {
                background: #fff;
                .news-item {
                  position: relative;
                  .news_pic {
                    img {
                      width: 100%;
                      max-height: 350px;
                    }
                  }
                  .news_tit {
                    position: absolute;
                    bottom: 0;
                    padding-top: 6px;
                    padding-bottom: 8px;
                    width: 100%;
                    background: #fff;
                    font-size: 16px;
                    line-height: 22px;
                    opacity: 0.9;
                    a {
                      display: block;
                      overflow: hidden;
                      padding-left: 15px;
                      color: #032f5a;
                      text-overflow: ellipsis;
                      white-space: nowrap;
                      font-weight: bolder;
                    }
                  }
                }
              }
            }
            .z_news_m {
              float: right;
              margin-left: 20px;
              width: 54%;
              .con_news_nav {
                margin-top: 10px;
                .post-news {
                  a {
                    display: block;
                    overflow: hidden;
                    color: #032f5a;
                    text-overflow: ellipsis;
                    white-space: nowrap;
                    font-size: 15px;
                    line-height: 43px;
                  }
                  .news-item {
                    position: relative;
                    overflow: hidden;
                    vertical-align: top;
                    border-bottom: #dfdede 1px solid;
                    .meta-title {
                      display: block;
                      overflow: hidden;
                      margin-right: 90px;
                    }
                    .meta-time {
                      position: absolute;
                      top: 50%;
                      right: 0;
                      display: block;
                      margin-top: -10px;
                      width: 80px;
                      height: 20px;
                      color: #999;
                      text-align: right;
                      line-height: 20px;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }

  // 底部内容
  .wp-container3 {
    background: url('../assets/img/bottom_frame_bg.png') center top no-repeat
      #0062cf;
    .wp-inner {
      padding: 68px 0 25px 0;
      background: url('../assets/img/logo-scdx.png') center center no-repeat;
      .left_frame {
        float: left;
        width: 28.6%;
        #wp_nav_w50 {
          padding-bottom: 45px;
          border-right: #bdbdbd 1px solid;
          .wp_nav {
            margin: 0;
            padding: 0;
            display: block;
            &:after {
              clear: both;
              content: '.';
              display: block;
              height: 0;
              visibility: hidden;
            }
            .nav-item {
              position: relative;
              vertical-align: bottom;
              // display: inline-block;
              width: 50%;
              float: left;
              a {
                display: block;
                width: auto;
                background: url('../assets/img/bottom_lead_vo.png') left center
                  no-repeat;
                color: #fff;
                text-align: left;
                font-size: 12px;
                .item-name {
                  display: inline-block;
                  padding: 5px 10px;
                  line-height: 22px;
                  cursor: pointer;
                }
              }
            }
          }
        }
      }
      .right_frame {
        float: right;
        width: 30.4%;
        border-left: #bdbdbd 1px solid;
        .share {
          float: right;
          margin-right: 0;
          padding: 6px 0;
          width: 123px;
          li {
            float: left;
            // display: inline-block;
            margin: 0 3px;
            text-align: center;
            a {
              color: #a4aeba;
              white-space: nowrap;
              display: inline-block;
              margin: 0 auto;
              width: 34px;
              height: 34px;
              background: url('../assets/img/share.png') no-repeat;
            }
          }
          .add-tqq a {
            background-position: -52px 0px;
          }
          .add-weibo a {
            background-position: -104px 0px;
          }
        }
        .bottom_link {
          float: right;
          .wp_nav {
            margin: 0;
            padding: 0;
            display: block;
            &:after {
              clear: both;
              content: '.';
              display: block;
              height: 0;
              visibility: hidden;
            }
            .nav-item {
              // display: inline-block;
              float: left;
              position: relative;
              vertical-align: bottom;
              a {
                background: url('../assets/img/bottom_lead_vo.png') left center
                  no-repeat;
                color: #fff;
                font-size: 12px;
                .item-name {
                  display: inline-block;
                  padding: 5px 10px;
                  line-height: 22px;
                  cursor: pointer;
                }
              }
            }
            .first-li a {
              background: 0 0;
            }
          }
        }
        .bottom_addr {
          float: right;
          p {
            color: #fff;
            text-align: right;
            font-size: 12px;
            line-height: 22px;
          }
        }
      }
    }
  }
}
</style>
