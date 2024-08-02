<template>
  <div class="">
    <!-- 내용을 추가하세요 -->
    <page-title title="1번 페이지" age="3" hobbies="['자전거','등산','꽃꽂이']"
    family="{papa:'아빠',mom:'엄마'}" :func="func"
    />
    <PageTitle v-bind:title="title1" v-bind:age="age" :family="family"/>
    <PageTitle :title="title2" :age="age" :hobbies="hobbies"/>
  </div>
  <div>
    <input type="text" v-model="hobby">
    <button @:click="addHobby">클릭</button>
  </div>
</template>

<script>
import PageTitle from '@/components/PageTitle.vue';
export default {
  name: 'TestView',
  props: {
    // 문자열 타입의 prop 예시
    //sampleString: {
    //  type: String,
    //  default: ''
    //},
    // 숫자 타입의 prop 예시
    //sampleNumber: {
    //  type: Number,
    //  default: 0
    //},
    // 배열 타입의 prop 예시
    //sampleArray: {
    //  type: Array,
    //  default: () => []
    //},
    // 객체 타입의 prop 예시
    //sampleObject: {
    //  type: Object,
    //  default: () => ({})
    //}
  },
  components: {
    PageTitle
    // 추가적으로 사용할 컴포넌트들을 등록합니다.
  },
  data() {
    return {
      // 컴포넌트의 데이터를 초기화합니다.
      title1:'page 1',
      title2:'page 2',
      age:3,
      hobby:'',
      hobbies:[],
      family:{
        papa:'아빠',
        mom:'엄마',
      }
    };
  },
  watch: {
    // sample1() {
    //   console.log('');
    // }
    // 데이터를 감시하고 처리할 로직을 작성합니다.
  },
  computed: {
    // sample2() {
    //   return '';
    // }
    // 필요한 계산된 속성을 정의합니다.
  },
  methods: {
    // sample3() {
    //   return '';
    // }
    // 컴포넌트에서 사용할 메서드를 정의합니다.
    addHobby(){
      this.hobbies.push(this.hobby);
      this.hobby='';
    },
  func(){
    return '결과';
  }
  },
  setup() {
    // Vue 3 Composition API의 setup 함수에서 추가적인 로직을 처리할 수 있습니다.
  },
  created() {
    // 컴포넌트가 생성될 때 실행될 로직을 작성합니다.
  },
  mounted() {
    // 컴포넌트가 DOM에 마운트된 직후 실행될 로직을 작성합니다.
  },
  unmounted() {
    // 컴포넌트가 파괴되기 전 실행될 로직을 작성합니다.
  }
};
</script>

<style scoped>
/* 스타일을 추가하세요 */
</style>