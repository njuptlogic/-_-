<template>
  <div class="home">
    <div class="header">
      <div class="header-left" style="display: flex;align-items: center;">
        <img src="@/assets/logop.png" alt="" style="height: 30px;margin-right: 10px;">本科生选题系统
      </div>
      <div class="header-right">
        <span v-for="item, index in title_list" :key="index" :class="{'active_title': active_title == index}" @click="changeActive(index)">
          {{ item.label }}
        </span>
      </div>
    </div>
    <div class="body">
      <StudentView v-if="active_title == 2"></StudentView>
      <TeacherView v-if="active_title == 1"></TeacherView>
      <ktView v-if="active_title == 0"></ktView>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import StudentView from './TeacherView/StudentView.vue';
import TeacherView from './TeacherView/TeacherView.vue';
import ktView from './TeacherView/ktView.vue';
export default {
  name: 'HomeView',
  components: {
    StudentView,
    TeacherView,
    ktView
  },
  data() {
    return {
      title_list: [
        {
          label: '我的课题'
        },
        {
          label: '课题详情'
        }
      ],
      active_title: 0
    }
  },
  methods: {
    changeActive: function(index) {
      this.active_title = index
    }
  }
}
</script>

<style lang="scss" scoped>
.home {
  text-align: left;
  width: 100%;
  height: 100%;
  position: fixed;
  display: flex;
  flex-direction: column;
  background: rgb(233, 233, 233);
  gap: 10px;
  .header {
    padding: 10px 20px;
    background: white;
    display: flex;
    align-items: center;
    border-radius: 20px;
    margin-top: 10px;

    &-left {
      color: blue;
      font-size: 28px;
      font-weight: 700;
    }

    &-right{
      flex: 1;
      padding-left: 700px;
      span{
        padding: 10px;
        margin: 0 20px;
        font-size: 20px;
        cursor: pointer;
        &.active_title{
          border-bottom:2px solid blue;
        }
      }
    }
  }

  .body{
    flex: 1;
    margin: 0 200px 20px 200px;
    background: white
  }

}
</style>
