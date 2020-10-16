<template>
  <div id="app">
    <!-- <div id="container">
      <button v-on:click="title = 'học lập trình vuejs'">Thay đổi title từ component App.vue</button>
      <compHeader 
        v-bind:titleHeader="title"
        v-on:changeTitleEvent="handleChangeTitle"
        v-bind:listUser="listUser"
      />
      <list-user
        v-on:AppdeleteUser = "AppdeleteUser"
        v-bind:listUser="listUser"/>
    </div> -->
    <!-- <demo-ref/> -->
    <!-- <demo-slot>
      <div class="app-slo">
        <p> 
          Xin chào các bạn, như chúng ta đã biết thì hiện nay 
          Vue.js là một trong những framework JavaScript tốt nhất và nhiều 
          người cho rằng Vue sẽ dần thay thế cho Angular và React trong tương 
          lai. Hôm nay mình sẽ tạo một vài ví dụ đơn giản với Vue-CLI.
        </p>
      </div> 
    </demo-slot> -->
    <demo-slot/>
  </div>
</template>

<script>
import CompHeader from "./components/CompHeader.vue";
import ListUser from "./components/ListUser.vue";
import DemoRef from "./components/DemoRef.vue";
import DemoSlot from "./components/DemoSlot.vue";
export default {
  name: "app",
  data() {
    return {
      title: "truyền dữ liệu từ cha(App) xuống con(CompHeader)",
      listUser: [
        { id: 1, email: "toan@gmail.com", active: true },
        { id: 2, email: "toan1@gmail.com", active: false },
        { id: 3, email: "toan2@gmail.com", active: true },
        { id: 4, email: "toan3@gmail.com", active: false },
        { id: 5, email: "toan4@gmail.com", active: true },
        { id: 6, email: "toan5@gmail.com", active: false }
      ]
      // msg: 'Welcome to Your Vue.js App'
    };
  },
  components: {
    CompHeader,
    ListUser,
    DemoRef,
    DemoSlot
  },
  methods: {
    handleChangeTitle(data) {
      //console.log("handleChangeTitle App.vue");
      this.title = data.title;
    },
    AppdeleteUser(data) {
      var indexDelete = -1;
      this.listUser.forEach((u, index) => {
        if (u.id === data.id) {
          indexDelete = index;
        }
      });
      if (indexDelete != -1) {
        this.listUser.splice(indexDelete, 1);
      }
      console.log("xóa id", data.id);
    }
  }
};
/*
Props Down -> truyền dữ liệu từ thằng cha vào thằng con->thằng con chỉ được 
dùng thôi. không được thay đổi trực tiếp.
Event Up -> Truyền sự kiện để thông báo cho component cha biết là nó muốn 
thay dữ liệu -> nhiệm vụ của component cha là nhận được thông điệp và tiến 
thay đổi data
->Custom Event trong Vuejs

click -> sự kiện có sẵn trong vuejs
V-on:click="changeTitle"
'click' -> tên sự kiện
'changeTitle' -> hàm sử lí
*/
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
