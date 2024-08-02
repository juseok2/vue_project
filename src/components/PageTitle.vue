<template>
  <div class="page_title">
    <!-- 내용을 추가하세요 -->
    <h2>Page Title</h2>
    <p>제목:{{title}}</p>
    <p>나이:{{age+1}}</p>
    <p>취미:{{hobbies}}</p>
    <p>부:{{family.papa}},모:{{family.mom}}</p>
    <p>함수결과:{{func()}}</p>
  </div>
</template>

<script>
export default {
  name: 'PageTitle',
  props: {
    title:{
      type: String,
      default:'제목없음',
    },
    age:{
      type: Number,
      default:0,
    },
    hobbies:{
      type: Array,
      default: () => ['바둑','낚시'],
    },
    family: {
     type: Object,
     default: () => ({})
    },
    func:{
      type: Function,
      default: function(){
        this.funcName='무명함수';
        return 'default func';
      }
    }

  },
  components: {
    // 추가적으로 사용할 컴포넌트들을 등록합니다.
  },
  data() {
    return {
      // 컴포넌트의 데이터를 초기화합니다.
      funcName:'',
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
.page_title{
  background-color: darksalmon;
}
</style>