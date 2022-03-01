const result = () => {
          const data = 13;
          if (data > 13) {
            if (data === 0) return "日";
            if (data === 1) return "月";
            if (data === 2) return "火";
            if (data === 3) return "水";
          } else if (data < 20) {
            if (data === 10) return "太陽";
            if (data === 11) return "水星";
            if (data === 12) return "金星";
            if (data === 13) return "地球";
          }
        };
        console.log(result());

<template>
  <div id="app" class="container mt-5">
    <h2>{{ title }}</h2>
    <div class="row">
      <div class="col-sm-8">
        <form @submit.prevent="submitForm">
          <div class="form-group">
            <label for="name">名前:</label>
            <input
              type="name"
              id="name"
              v-model="name"
              @blur="$v.name.$touch()"
              :class="{ error: $v.name.$error, 'form-control': true }"
            />
            <span v-if="$v.name.$error">名前が入力されていません。</span>
          </div>
          <div class="form-group">
            <label for="age">年齢:</label>
            <input
              type="age"
              id="age"
              v-model="age"
              @blur="$v.age.$touch()"
              :class="{ error: $v.age.$error, 'form-control': true }"
            />
            <div v-if="$v.age.$error">
              <span v-if="!$v.age.required">年齢が入力されていません。</span>
              <span v-if="!$v.age.integer"
                >整数の数字以外は入力できません。</span
              >
            </div>
          </div>
          <div class="form-group">
            <label for="email">メールアドレス:</label>
            <input
              type="email"
              id="email"
              v-model="email"
              @blur="$v.email.$touch()"
              :class="{ error: $v.email.$error, 'form-control': true }"
            />
            <div v-if="$v.email.$error">
              <span v-if="!$v.email.required"
                >メールドレスが入力されていません。</span
              >
              <span v-if="!$v.email.email"
                >メールアドレスの形式が正しくありません。</span
              >
            </div>
          </div>
          <button type="submit" class="btn btn-info">送信</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
Vue.use(window.vuelidate.default);
const { required, email, integer } = window.validators;

const app = new Vue({
  el: "#app",
  data: {
    title: "入力フォームバリデーション",
    name: "",
    age: "",
    email: "",
  },
  validations: {
    name: {
      required,
    },
    email: {
      required,
      email,
    },
    age: {
      required,
      integer,
    },
  },
  methods: {
    submitForm() {
      this.$v.$touch();
      if (this.$v.$invalid) {
        console.log("バリデーションエラー");
      } else {
        // データ登録の処理をここに記述
        console.log("submit");

        
      }
    },
  },
});
</script>