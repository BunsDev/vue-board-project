<template>
    <div id="mainWrapper">
      <h4>
        <label><input name="boardSelectByLvl" type="checkbox" value="selectParents" v-model="boardSelectByLvl" checked="checked"> 최상위 계층 게시글 선택(부모 게시글) </label>
        <label><input name="boardSelectByLvl" type="checkbox" value="selectChild" v-model="boardSelectByLvl" checked="checked"> 최상위 계층이 아닌 게시글 선택(자식 게시글) </label>
      </h4>
      <label><input name="soryType" type="radio" v-bind:value="sortByOrder" v-model="sortType" checked="checked"> 게시글 계층 정렬 </label>
      <label><input name="soryType" type="radio" v-bind:value="sortByRegDt" v-model="sortType"> 게시글 최신순 정렬 </label>
      <label><input name="soryType" type="radio" v-bind:value="sortByNormal" v-model="sortType"> 게시글 정렬 </label>
        <h1>
          <span>{{ sortType }}: {{ boardSelectByLvl }} </span>
        </h1>
        <h3>접속유저 : {{ userId }} </h3>
          <table class="board_table">
            <colgroup>
              <col width="10%" />
              <col width="40%" />
              <col width="15%" />
              <col width="15%" />
              <col width="10%" />
              <col width="10%" />
            </colgroup>
            <thead>
              <tr>
                <th scope="cols">번호</th>
                <th scope="cols">제목</th>
                <th scope="cols">작성자</th>
                <th scope="cols">작성일</th>
                <th scope="cols">조회수</th>
                <th scope="cols">댓글수</th>
              </tr>
            </thead>
            <tbody>
              <tr :key="i" v-for="(board, i) in boardList">
                <th scope="row">{{ i+1 }}</th>
                <td>{{ board.brdTitle }}</td>
                <td>{{ board.brdWriter }}</td>
                <td>{{ board.brdRegDt }}</td>
                <td>{{ board.brdHit }}</td>
                <td>{{ board.brdReCnt }}</td>
              </tr>
            </tbody>
          </table>
    </div>
    <li id='liSearchOption'>
    <div>
        <select id='selSearchOption' >
            <option value='A'>제목+내용</option>
            <option value='T'>제목</option>
            <option value='C'>내용</option>
        </select>
        <input id='txtKeyWord' />
        <input type='button' value='검색'/>
    </div>
    </li>
</template>
<script>
export default {
  components: {},
  data () {
    return {
      isActive: true,
      hasError: true,
      styleObject: {
        color: 'red',
        fontSize: '13px'
      },
      sortByOrder: '게시글 계층 정렬',
      sortByRegDt: '게시글 최신순 정렬',
      sortByNormal: '게시글 정렬',
      userId: 'test_id',
      boardList: [
        { brdTitle: '테스트 글제목', brdWriter: 'foo', brdRegDt: '2022-03-31', brdHit: '3', brdReCnt: '0' },
        { brdTitle: '테스트 글제목', brdWriter: 'foo', brdRegDt: '2022-03-31', brdHit: '3', brdReCnt: '0' },
        { brdTitle: '테스트 글제목', brdWriter: 'foo', brdRegDt: '2022-03-31', brdHit: '3', brdReCnt: '0' }
      ],
      sortType: '게시글 계층 정렬',
      selectChild: '자식선택',
      selectParents: '부모선택',
      boardSelectByLvl: []
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
  ul, li{
    list-style:none;
    text-align:center;
    padding:0;
    margin:0;
  }
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
  #liSearchOption {
    clear:both;
  }
  #liSearchOption > div {
    margin:0 auto;
    margin-top: 30px;
    width:auto;
    height:100px;
  }
  .left {
    text-align : left;
  }
</style>
