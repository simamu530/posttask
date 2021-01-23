<template>
  <div id="app">
    <CommonHeader></CommonHeader>
    <main>
      <div id="task">
        <ul>
          <li>
      件名：<input type="text" v-model="title" />
          <!-- <p>{{ title }}</p> -->
          </li>
          <li>
      依頼主：<input type="text" v-model="name" />
          </li>
          <li>
      納期：<input type="number" v-model="month">/<input type="number" v-model="day">
          </li>
          <li>
      内容：<input type="text" v-model="contents">
          </li>
      <button @click="addTask()">掲載する</button>
        </ul>
      </div>
      <div id="result">
        <p v-for="(item, Index) in items" v-bind:key="Index">{{ item }}</p>
      </div>
    </main>
    <common-footer></common-footer>
  </div>
</template>

<script>
import CommonFooter from '../../posttask/src/components/CommonFooter.vue'
import CommonHeader from '../../posttask/src/components/CommonHeader.vue'


export default {
  name: 'App',
  components: {
    CommonHeader,
    CommonFooter
  },
  data() {
    return {
      items:[],
      title: '',
      name: '',
      day: '',
      month: '',
      contents: '',
    };
  },
  methods:{
    addTask :function() {
      this.items.length=0
      this.items.push(this.title, this.name, this.month, this.contents);
      this.title=""
      console.log(this.items)
      }
    }
};

</script>

<style>
@charset "UTF-8";

/*
html5doctor.com Reset Stylesheet
v1.6.1
Last Updated: 2010-09-17
Author: Richard Clark - http://richclarkdesign.com
Twitter: @rich_clark
*/

html,
body,
div,
span,
object,
iframe,
h1,
h2,
h3,
h4,
h5,
h6,
p,
blockquote,
pre,
abbr,
address,
cite,
code,
del,
dfn,
em,
img,
ins,
kbd,
q,
samp,
small,
strong,
sub,
sup,
var,
b,
i,
dl,
dt,
dd,
ol,
ul,
li,
fieldset,
form,
label,
legend,
table,
caption,
tbody,
tfoot,
thead,
tr,
th,
td,
article,
aside,
canvas,
details,
figcaption,
figure,
footer,
header,
hgroup,
menu,
nav,
section,
summary,
time,
mark,
audio,
video {
  margin: 0;
  padding: 0;
  border: 0;
  outline: 0;
  font-size: 100%;
  vertical-align: baseline;
  background: transparent;
}

body {
  line-height: 1.6;
}

article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
menu,
nav,
section {
  display: block;
}

nav ul {
  list-style: none;
}

blockquote,
q {
  quotes: none;
}

blockquote:before,
blockquote:after,
q:before,
q:after {
  content: "";
  content: none;
}

a {
  margin: 0;
  padding: 0;
  font-size: 100%;
  vertical-align: baseline;
  background: transparent;
}

/* change colours to suit your needs */
ins {
  background-color: #ff9;
  color: #000;
  text-decoration: none;
}

/* change colours to suit your needs */
mark {
  background-color: #ff9;
  color: #000;
  font-style: italic;
  font-weight: bold;
}

del {
  text-decoration: line-through;
}

abbr[title],
dfn[title] {
  border-bottom: 1px dotted;
  cursor: help;
}

table {
  border-collapse: collapse;
  border-spacing: 0;
}

/* change border colour to suit your needs */
hr {
  display: block;
  height: 1px;
  border: 0;
  border-top: 1px solid #cccccc;
  margin: 1em 0;
  padding: 0;
}

input,
select {
  vertical-align: middle;
}
</style>
