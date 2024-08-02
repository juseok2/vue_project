<template>
  <div class="basic">
    <h3>----------------value값 연결----------------</h3>
    <h3>Hello, {{title}}</h3>
    <h3>{{title}}는 수원시 장안구에 있습니다.</h3>
    <p>{{message}}</p>
    <p v-html="message"></p>
  </div>
  <div>
    <input type="text" v-model="nickname">
  </div>
  <div>
    <input type="number" v-model="age">
  </div>
  <div>
    <textarea v-model="message" cols="30" rows="10"></textarea>
  </div>
  <div>
    <select name="city" v-model="city">
      <option value="01">서울</option>
      <option value="02">부산</option>
      <option value="03">대구</option>
      <option value="04">수원</option>
    </select>
  </div>
  
  <div>
    <label>
    <input type="checkbox" v-model="cbox">{{cbox}}
    </label>
    <br>
    <label>
    <input type="checkbox" v-model="cbox2" true-value="동의" false-value="비동의">{{cbox2}}
    </label>
  </div>
  <div>
    <p>좋아하는 음식은?</p>
    <label>
    <input type="checkbox" v-model="goodfood" value="마라탕">마라탕
    </label>
    <label>
    <input type="checkbox" v-model="goodfood" value="민트초코">민트초코
    </label>
    <label>
    <input type="checkbox" v-model="goodfood" value="홍어삼합">홍어삼합
    </label>
    
    <p>당신이 좋아하는 음식은 {{goodfood}} 입니다.</p><br>
    <p>싫어하는 음식은?</p>
    <label>
    <input type="checkbox" v-model="badfood" value="마라탕">마라탕
    </label>
    <label>
    <input type="checkbox" v-model="badfood" value="민트초코">민트초코
    </label>
    <label>
    <input type="checkbox" v-model="badfood" value="홍어삼합">홍어삼합
    </label>
    <p>당신이 싫어하는 음식은 {{badfood}}입니다.</p>
  </div>
  <div>
    <p>당신의 성별은?</p>
    <label><input type="radio" v-model="gender" value="남" checked="true">남</label>
    <label><input type="radio" v-model="gender" value="여">여</label>
    <p>당신은 {{gender}}자 입니다.</p>
  </div>

  <h3>----------------속성 연결----------------</h3>
  <div>
     <img v-bind:src="imgSrc" alt="" v-bind:title="tooltip"/>
  </div>
  <div>
    <button v-bind:disabled="show">눌러주세요</button>
    <button v-bind:disabled="show2">눌러주세요</button>
  </div>
  <div>
    <button v-bind:style="btn1">눌러주세요</button>
    <button v-bind:style="btn2">눌러주세요</button>
  </div>
  <h3>----------------제어문(v-if,v-for)----------------</h3>
  <div>
    <table>
      <thead>
        <tr>
          <th>제품명</th>
          <th>가격</th>
          <th>카테고리</th>
          <th>배송료</th>
        </tr>
      </thead>
      <tbody>
        <tr v-bind:key = "index" v-for="(item, index) in products">
          <td>{{item.name}}</td>
          <td>{{item.price}}</td>
          <td>{{item.category}}</td>
          <td>{{item.delivery}}</td>
        </tr>
      </tbody>
    </table>
  </div>
  <div>
    <!-- v-if 요소를 만드느냐 안만드느냐 -->
    <p v-if="true">if참인때</p>
    <p v-if="false">if거짓인때</p>
    <!-- v-show 요소는 만들고, 보여주냐 안보여주냐 -->
    <p v-show="true">show참인때</p>
    <p v-show="false">show거짓인때</p>
  </div>
  <h3>----------------이벤트처리(v-on)----------------</h3>
  <div>
    <button v-on:click="increaseCounter">클릭(증가)</button>
    <button @:click="decreaseCounter">클릭(감소)</button>
    <p>counter:{{counter}}</p>
    <input type="number" v-model="countValue">
    <button @:click="applyCounter">적용</button>

    <button @:click="increaseCounter(),showMsg()">증가후 알림창</button>
    <button @:click="decreaseCounter(),showMsg()">감소후 알림창</button>
  </div>

  <div>
    <select v-model="cityValue" @:change="changeCity">
      <option value="서울">서울</option>
      <option value="부산">부산</option>
      <option value="대구">대구</option>
      <option value="수원">수원</option>
    </select>
  </div>
  <br><br>
  <div>
    <input type="text" v-model="emailValue" @input="changeEmail" placeholder="이메일을 입력하세요">
    <p>{{emailValue}}</p>
    <p v-if="errEmail">{{errEmail}}</p>
  </div>
  <br><br>
  <div>
    <input type="text" v-model="pwdValue1" @input="changePwd1" placeholder="비밀번호를 입력하세요"><br>
    <input type="text" v-model="pwdValue2" @input="changePwd2" placeholder="비밀번호확인을 입력하세요"><br>
    <p v-if="errPwd">{{errPwd}}</p>
  </div>

  <div>
    <p>{{hello()}}</p>
    <p>{{hello()}}</p>
    <p>{{hello()}}</p>
    <p>{{hello2}}</p>
    <p>{{hello2}}</p>
    <p>{{hello2}}</p>
  </div>
  <div>
    성: <input type="text" v-model="lastName" @:input="changeLastName"><br>
    이름: <input type="text" v-model="firstName" @:input="changeFirstName"><br>
    <p>method: {{methodFullName()}}</p>
    <p>method: {{methodFullName()}}</p>
    <p>computed: {{computedFullName}}</p>
    <p>computed: {{computedFullName}}</p>
    <p>fullName: {{fullName}}</p>
    <p>fullName: {{fullName}}</p>
    
  </div>

  <!-- watch -->
  <div>
    <h4>name_info:{{userInfo}}</h4>
    <input type="text" v-model="userName">
    <input type="text" v-model="userAge">
  </div>

  <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
  끝
</template>

<script>
export default {
  name: 'BasicView',
  components: {
    
  },
  data() {
    return {
      title:"연세IT",
      message:"<b>연세IT</b>는 <b><span style='color:red;'>5년</span></b> 우수직업학교입니다.",
      nickname:"돌쇠",
      age:22+3,
      city:"04",
      cbox: false,
      cbox2:"비동의",
      goodfood:[],
      badfood:[],
      gender:"남",
      imgSrc:"https://borgssam.github.io/MySite/img/album_01.jpg",
      tooltip:"툴팁메시지",
      show:true,
      show2:false,
      btn1: {
        backgroundColor:'blue',
        color:'yellow',
        fontSize:'32px',
      },
      btn2: {
        backgroundColor:'red',
        color:'skyblue',
        fontSize:'32px',
      },
      products:[
        {
          "name":"마우스",
          "price":2500,
          "category":"pc용품",
          "delivery":3000
        },
        {
          "name":"마우스2",
          "price":2500,
          "category":"pc용품",
          "delivery":3000
        },
        {
          "name":"마우스3",
          "price":2500,
          "category":"pc용품",
          "delivery":3000
        }
      ],
      counter:0,
      countValue:10,
      cityValue:"수원",
      emailValue:'',
      errEmail:'',
      pwdValue1:'',
      pwdValue2:'',
      errPwd:'비밀번호를 입력하세요',
      lastName:'',
      firstName:'',
      fullName:'',
      userName:'홍길동',
      userAge:'30',
      uaerInfo:'',
    };
  },
  watch:{
    userName(){
      this.userInfo = this.userName+'('+this.userAge+')';
    },
    userAge(){
      this.userInfo = this.userName+'('+this.userAge+')';
    }
  },
  setup() {
    
  },
  created() {
    
  },
  mounted() {

  },
  unmounted() {
    
  },
  computed:{
    hello2(){
      console.log('hello02()호출')
      return '안녕하세요 반가워요';
    },
    computedFullName(){
      console.log("computedFullName호출");
      return this.lastName+this.firstName;
    }
  },
  methods: {
    increaseCounter(){
      this.counter = this.counter +1;
    },
    decreaseCounter(){
      this.counter = this.counter -1;
    },
    applyCounter(){
      this.counter = this.countValue;
    },
    showMsg(){
      alert('현재값 = >'+ this.counter );
    },
    changeCity(){
      alert('선택하신 도시는 '+this.cityValue+'입니다.');
    },
    changeEmail(){
      console.log(123546);
      const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      if(this.emailValue === '' || emailPattern.test(this.emailValue)){
        this.errEmail='';
      }else{
        this.errEmail='이메일 형식에 어긋납니다.'
      }
    },
    changePwd1(){
      if(this.pwdValue1===''){
        this.errPwd ='비밀번호를 입력하세요';
      }else if(this.pwdValue1.length<8){
        this.errPwd ='비밀번호를 8자 이상 입력하세요';
      }
      else if(this.pwdValue2===''){
        this.errPwd ='비밀번호확인을 입력하세요';
      }else if(this.pwdValue1===this.pwdValue2){
        this.errPwd ='';
      }else{
        this.errPwd ='비밀번호가 일치하지 않습니다.';
      }
    },
    changePwd2(){
      if(this.pwdValue1===''){
        this.errPwd ='비밀번호를 입력하세요';
      }else if(this.pwdValue2===''){
        this.errPwd ='비밀번호확인을 입력하세요';
      }else if(this.pwdValue1===this.pwdValue2){
        this.errPwd ='';
      }else{
        this.errPwd ='비밀번호가 일치하지 않습니다.';
      }
    },
    hello(){
      console.log('hello()호출');
      return '안녕하세요 반갑습니다.'
    },
    changeLastName(){
      console.log("changeLastName호출");
      this.fullName=this.lastName+this.firstName;
      console.log(this.fullName);
    },
    changeFirstName(){
      console.log("changeFirstName호출");
      this.fullName=this.lastName+this.firstName;
    },
    methodFullName(){
      console.log("methodFullName호출");
      return this.lastName+this.firstName;
    }
  }
};
</script>

<style scoped>
table{
  border-collapse: 0;
  width: 50%;
  margin: 0 auto;
}
td,th{
  border: 1px solid #ddd;
  text-align: left;
  padding: 8px;
}
th{
  text-align: center;
  font-weight: 600;
}
@media screen and (max-width: 800px){
  table{
  width: 80%;
  margin: 0 auto;
}
}
</style>