<script setup>
import { SidebarComponent as EjsSidebar } from '@syncfusion/ej2-vue-navigations';
import { ButtonComponent as EjsButton } from "@syncfusion/ej2-vue-buttons";
import { ListViewComponent as EjsListview } from '@syncfusion/ej2-vue-lists';
import { ref } from 'vue';
const sidebar = ref(null);
const listData = [
    { 
      id: "1", 
      text: "JavaScript", 
      description: "JavaScript (JS) is an interpreted computer programming language. " +
        "It was originally implemented as part of web browsers so that client-side scripts" + 
        "could interact with the user, control the browser, communicate asynchronously, and" +
        "alter the document content that was displayed." },
    { 
      id: "2",
      text: "TypeScript", 
      description: "TypeScript is a typed superset of JavaScript that compiles to plain JavaScript." + 
        "TypeScript is an open-source, object-oriented programing language."},
    { 
      id: "3",
      text: "Angular", 
      description: "Angular is a platform and framework for building single-page client applications using HTML and TypeScript." +
        " Angular is written in TypeScript." },
    { 
      id: "4",
      text: "React",
      description: "React is a declarative, efficient, and flexible JavaScript library for building user interfaces." +
        " It lets you compose complex UIs from small and isolated pieces of code called “components”." },
    { 
      id: "5",
      text: "Vue", 
      description: "Vue is incrementally adoptable." +
        " The core library is focused on the view layer only and is easy to pick up and integrate with other" +
        " libraries or existing projects." 
    }
  ];
  const listFields = {
    id:"id", text: "text"
  };

const buttonClick = () => {
  sidebar.value.toggle();
};

const onSelect = (args) => {
  const mainContent = document.getElementsByClassName("main-content")[0];
  if(mainContent) {
    mainContent.innerHTML = args.data.description;
  }
};

</script>

<template>
<div>
  <div class="header">
    <span style="float:left;" >
      <ejs-button class="customBtn" iconCss="e-icons e-menu"
      v-on:click="buttonClick">Language</ejs-button>
    </span>
    <span>Header</span>
  </div>
  <ejs-sidebar width="250px">
    <div class="sidebar-content">      
      <ejs-listview
      :dataSource='listData' :fields='listFields'>
      </ejs-listview>
    </div>
  </ejs-sidebar>
  <div class="main-content">
     Main Content
  </div>
</div>
</template>

<style>
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-navigations/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-buttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-lists/styles/material.css";
.header {
  text-align: center;
  color: white;
  background-color: midnightblue;
  line-height: 51px;
  font-size: 25px;
}

.main-content {
    font-family: "Roboto";
    font-size: 20px;
    text-align: center;
    padding-top: 30px;
    padding-left: 30px;
}

.sidebar-content {
  font-size: 25px;
  text-align: center;
 /* padding-top: 50px;*/
}

.e-sidebar.e-left {
    top: 60px;
    left: 8px
}
.e-sidebar.e-right {
  top: 60px;
}

.customBtn {
  color: white !important;
  background-color: midnightblue !important;
  border-color: midnightblue !important;
}
</style>
