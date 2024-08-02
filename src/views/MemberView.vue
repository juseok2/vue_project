<template>
  <div class="member">
    <div>
      <h2>회원가입</h2>
      <h3>사용자이름</h3>
      <label><input type="text" id="user"></label>
      <h3>이메일</h3>
      <label><input type="text" id="email"></label>
      <h3>비밀번호</h3>
      <label><input type="password" id="password"></label>
      <h3>비밀번호 확인</h3>
      <label><input type="password" id="password"></label>
      <h3>성별</h3>
      <div>
        <label><input type="radio" name="gender">남성</label>
        <label><input type="radio" name="gender">여성</label>
      </div>
      <h3>좋아하는 음식</h3>
      <select name="" id="food">
        <option value="01">한식</option>
        <option value="01">중식</option>
        <option value="01">양식</option>
        <option value="01">일식</option>
      </select>
      <label id="info"><input type="checkbox">정보공개 동의</label>
      <button>가입하기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MemberView',
  components: {
    
  },
  data() {
    return {
      
    };
  },
  setup() {
    
  },
  created() {
    
  },
  mounted() {
    
  },
  unmounted() {
    
  },
  methods: {
    
  }
};
</script>

<style scoped>
  .member>div{
    width: 500px;
    background-color: white;
    margin: 40px auto;
    padding: 40px;
    text-align: left;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 0px 0px 3px 2px #ccc;
  }
  #user,#email,#password{
    width: 500px;
    height: 40px;
    font-size: 16px;
  }
  #food{
    width: 500px;
    height: 40px;
  }
  #info{
    display: block;
    margin: 10px 0;
  }
  button{
    display: block;
    margin: 0 auto;
    background-color: rgb(0, 119, 255);
    border: none;
    border-radius: 5px;
    padding: 15px 30px;
    color: white;
    cursor: pointer;
    transition: all 0.3s ease-in-out;
  }
  button:hover{
    background-color: rgb(0, 87, 185);
  }
</style>