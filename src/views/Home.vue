<template>
<div>
<div class="dashboard">
<h1 class="subheading grey--text">Dashboard</h1>
<v-container>
<v-card flat class='pa-3' v-for="project in projects" :key="project.title">
<v-layout row wrap :class="`project ${project.status}`">
<v-flex xs12 md6>
<div class='caption grey--text'>project title</div>
<div>{{project.title}}</div>
</v-flex>
<v-flex xs6 md2>
<div class='caption grey--text'>person</div>
<div>{{project.person}}a</div>
</v-flex>
<v-flex xs6 md2>
<div class='caption grey--text'>Due by</div>
<div>{{project.due}}</div>
</v-flex>
<v-flex xs6 md2>
<div class='caption grey--text'>Status</div>
<div>{{project.status}}</div>
</v-flex>
</v-layout>
<v-divider></v-divider>
</v-card>
</v-container>
</div>
</div>
</template>
<script>
export default{
data(){
return{

projects:[
{title:'interior design',person:'opicho',due:'1st jan 2019',status:'ongoing'},
{title:'software architect',person:'ngoroboi',due:'1st jan 2018',status:'pending'},
{title:'aero space engineer',person:'Ann',due:'3rd jan 2019',status:'ongoing'}
]

}
}
}
</script>
<style>
.project.ongoing{
border-left:4px solid #3cd1c2;
}
.project.pending{
border-left:4px solid red;
}
</style>
