<template>
    <img v-bind:src="imgSrc" />
    <h1>Hello, {{ title }}!</h1>
    <div>{{ htmlString }}</div>
    <div v-html="htmlString"></div>
    <br>
    <input type="text" v-model="valueModel" />
    <br>
    <input type="number" v-model.number="numberModel" />
    <br>
    <textarea v-model="message"></textarea>
    <br>
    <select v-model="city">
      <option value="02">서울</option>
      <option value="21">부산</option>
      <option value="064">제주</option>
    </select>
    <br>
    <label><input type="checkbox" value="서울" v-model="checked"> 서울 </label>
    <label><input type="checkbox" value="부산" v-model="checked"> 부산 </label>
    <label><input type="checkbox" value="제주" v-model="checked"> 제주 </label>
    <br>
    <span>체크한 지역 : {{ checked }} </span>
    <br>
    <label><input type="radio" v-bind:value="radioValue1" v-model="picked"> 서울 </label>
    <label><input type="radio" v-bind:value="radioValue2" v-model="picked"> 경기 </label>
    <label><input type="radio" v-bind:value="radioValue3" v-model="picked"> 인천 </label>
    <br>
    <span>체크한 지역 : {{ picked }} </span>
    <br>
    <div>
      <input type="text" v-model="textValue" />
      <button type="button" v-bind:disable="textValue==''">Click</button>
      {{ textValue }}
    </div>
    <div class="container" v-bind:class="{
      'active': isActive, 'text-red': hasError
      }">Class binder,       {{ hasError }}</div>
    <div v-bind:style="[styleObject]">인라인 스타일 바인딩</div>
</template>
<script>
export default {
  data () {
    return {
      title: 'world',
      htmlString: '<p style="color:red;">This is a red String.</p>',
      valueModel: 'South Korea',
      numberModel: 3,
      message: '여러 줄을 입력할 수 있는 textarea 입니다.',
      city: '064',
      checked: [],
      picked: '',
      radioValue1: '서울',
      radioValue2: '경기',
      radioValue3: '인천',
      imgSrc: 'https://kr.vuejs.org/images/logo.png',
      textValue: '',
      isActive: true,
      hasError: true,
      styleObject: {
        color: 'red',
        fontSize: '13px'
      }
    }
  },
  beforeCreate () {},
  created () {},
  beforeMount () {},
  mounted () {},
  beforeUpdate () {},
  updated () {},
  beforeUnmount () {},
  unmounted () {},
  methods: {}
}
</script>
<style scoped>
  container {
    width: 100%;
    height: 200px;
  }
  .active {
    background-color: yellow;
    font-weight: bold;
  }
  .text-red {
    color: red;
  }
  table.board_table {
    table-layout: auto;
    width: 100%;
    border-collapse: collapse;
    text-align: center;
    line-height: 1.5;
  }
  table.board_table thead th {
    padding: 10px;
    font-weight: bold;
    vertical-align: top;
    color: #369;
    border-bottom: 3px solid #036;
  }
  table.board_table tbody th {
    width: 150px;
    padding: 10px;
    font-weight: bold;
    vertical-align: top;
    border-bottom: 1px solid #ccc;
    background: #f3f6f7;
  }
  table.board_table td {
    width: 350px;
    padding: 10px;
    vertical-align: top;
    border-bottom: 1px solid #ccc;
  }
</style>
