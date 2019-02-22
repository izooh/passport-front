<template>
<div>
<div class="dashboard">
<h1 class="subheading grey--text">Dashboard</h1>
<v-container >
<v-layout row class="mb-3">
<v-tooltip top>
<v-btn small flat color="grey" @click="sortBy('title')" slot="activator">
<v-icon small left>folder</v-icon>
<span class="caption text-lowercase">By project Name</span>
</v-btn>
<span>sorting items by project name</span>
</v-tooltip>
<v-tooltip top>
<v-btn small flat color="grey" @click="sortBy('person')" slot="activator">
<v-icon small left>person</v-icon>
<span class="caption text-lowercase">By person</span>
</v-btn>
<span>sorting items by project person name</span>
</v-tooltip>
</v-layout>
<v-card flat class='pa-3' v-for="project in projects" :key="project.title">
<v-layout row wrap :class="`project ${project.status}`">
<v-flex xs12 md6>
<div class='caption grey--text'>project title</div>
<div>{{project.title}}</div>
</v-flex>
<v-flex xs6 md2>
<div class='caption grey--text'>person</div>
<div>{{project.person}}</div>
</v-flex>
<v-flex xs6 md2>
<div class='caption grey--text'>Due by</div>
<div>{{project.due}}</div>
</v-flex>
<v-flex xs6 md2>
<div class="right">
<v-chip small :class="`${project.status} white--text caption my-2`">
{{project.status}}
</v-chip>
</div>

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
{title:'aero space engineer',person:'Ann',due:'3rd jan 2019',status:'ongoing'},
{title:'chemist',person:'newton',due:'3rd jan 2019',status:'pending'}
]

}
},
methods:{
sortBy(prop){
this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
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
.v-chip.ongoing{
border:12px solid #3cd1c2;
}
.v-chip.pending{
border:12px solid red;
}
</style>
