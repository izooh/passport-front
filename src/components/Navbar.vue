<template>
<div>
<nav>
<v-toolbar flat app>
<v-toolbar-side-icon class='grey--text' @click='drawer=!drawer'></v-toolbar-side-icon>
<v-toolbar title flat class="text-uppercase grey--text">
<span class="font-weight-dark">Pass</span>
<span>port</span>
</v-toolbar title>
<v-btn flat color="grey">
<span>Sign Out</span>
<v-icon right>exit_to_app</v-icon>
</v-btn>
</v-toolbar>
<v-navigation-drawer v-model='drawer' flat app class='blue lighten-3'>
<v-list>
<v-list-tile v-for='link in links' :key='link.text' router :to="link.route">
<v-list-tile-action>
<v-icon class='white--text'>{{link.icon}}</v-icon>
</v-list-tile-action>
<v-list-tile-content>
<v-list-tile-title class='white--text'>{{link.text}}</v-list-tile-title>
</v-list-tile-content>
</v-list-tile>
</v-list>
</v-navigation-drawer>
</nav>
</div>
</template>
<script>
export default{
data(){
return{
drawer: false,
links:[
{icon:'dashboard',text:'Dashboard',route:'/'},
{icon:'store',text:'Myprojects',route:'/about'},
{icon:'person',text:'Team',route:'/team'}
]

}
}

}
</script>
