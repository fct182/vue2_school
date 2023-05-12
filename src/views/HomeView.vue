<template>
  <div class="home-view">
    <!-- 头部 -->
    <div class="wp-wrapper top-header">
      <div class="wp-inner clearfix">
        <!--副导航开始-->
        <div class="wp-panel top-nav-panel" frag="左侧导航">
          <div class="" frag="左侧导航">
            <ul class="wp-menu clearfix">
              <li class="menu-item">
                <a class="menu-link">在校学生</a>
              </li>
              <li class="menu-item">
                <a class="menu-link">教职员工</a>
              </li>
              <li class="menu-item">
                <a class="menu-link">校友</a>
              </li>
              <li class="menu-item">
                <a class="menu-link">未来学生</a>
              </li>
              <li class="menu-item">
                <a class="menu-link">学生家长</a>
              </li>
              <li class="menu-item">
                <a class="menu-link">公众访客</a>
              </li>
            </ul>
          </div>
        </div>
        <!--//副导航结束-->
        <div style="width: 50%; float: right" class="clearfix asd">
          <!--搜索开始-->
          <div class="wp-panel panel-3" frag="面板3">
            <a href="javascript:void(0)" id="myBtn"></a>
          </div>
          <!--//搜索结束-->
          <!--右侧导航开始-->
          <div class="wp-panel lang-panel panel-2" frag="右侧导航">
            <div class="wp-window lang-window window-2" frag="右侧导航">
              <ul class="wp-menu clearfix" data-nav-aside='{"title":"语言","index":2}'>
                <li class="menu-item i1">
                  <a class="menu-link">OA</a>
                </li>
                <li class="menu-item i2">
                  <a class="menu-link">西华易班</a>
                </li>
                <li class="menu-item i3">
                  <a class="menu-link">教务系统</a>
                </li>
                <li class="menu-item i4">
                  <a class="menu-link">教师邮件</a>
                </li>
                <li class="menu-item i5">
                  <a class="menu-link">学生邮件</a>
                </li>
                <li class="menu-item i6">
                  <a class="menu-link">办事大厅</a>
                </li>
                <li class="menu-item i7">
                  <a class="menu-link">图书馆</a>
                </li>
                <li class="menu-item i8">
                  <a class="menu-link">English</a>
                </li>
              </ul>
            </div>
          </div>
          <!--//右侧导航结束-->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeView'
};
</script>

<style lang="scss">
.home-view {
  .wp-wrapper {
    width: 100%;
    .wp-inner {
      margin: 0 auto;
      width: auto;
      max-width: 1200px;
    }
  }
  .top-header {
    background: #004c7e;
  }
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
  .panel-3 {
    position: relative;
    float: right;
    margin-right: 10px;
  }
  #myBtn {
    display: block;
    padding-top: 11px;
    width: 24px;
    height: 24px;
    background: url('../assets/img/search.png') center center no-repeat;
  }
  .lang-panel {
    float: left;
    margin-right: 10px;
  }
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
</style>
