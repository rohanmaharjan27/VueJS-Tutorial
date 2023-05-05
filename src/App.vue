<template>
  <div>{{ name }}</div>
  <div v-html="title"></div>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="buttonDisabled">Bind</button>
  <h2 class="underline">Underlined</h2>
  <div class="underline" v-bind:class="status">Success</div>
  <div v-bind:class="isPromoted ? 'promoted' : 'notPromoted'">Promoted</div>
  <div v-bind:class="['underline','promoted']">Underlined and Promoted</div>
  <div v-bind:class="['underline', isPromoted && 'promoted']">Array Conditional Class</div>
  <div v-bind:class="{promoted: isPromoted}">Object Conditional Class</div>

  <!-- Using v-bind shorthand -->
  <div :style="{color: highlightColor, 'font-size': fontSize}">Inline Styles</div>
  <h2 :style="headerStyleObject">Styled Object</h2>
  <h2 :style="[baseStyleObject, successStyleObject]">Styled Array</h2>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      name: 'Rohan',
      title: '<b>VueJS Tutorial</b>',
      headingId:'heading',
      buttonDisabled: true,
      status: 'success',
      isPromoted: true,
      highlightColor: 'yellow',
      fontSize: '20px',
      headerStyleObject: {
        color: 'orange',
        fontSize: '20px',
        padding: '10px',
      },
      baseStyleObject: {
        fontSize: '20px',
        padding: '10px',
      },
      successStyleObject:{
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green',
      }
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline{
  text-decoration: underline;   
}

.success{
  color: green;
}

.promoted{
  color: blue;
  font-weight: bold;
}

.notPromoted{
  color: black;
}
</style>
