<template>
<q-layout>
  <!-- Header -->
  <div slot="header" class="toolbar">
    <!-- opens left-side drawer using its ref -->
    <button class="hide-on-drawer-visible" @click="$refs.leftDrawer.open()">
      <i>menu</i>
    </button>
    <q-toolbar-title :padding="1">
      {{ title }}
    </q-toolbar-title>
    <!-- opens right-side drawer using its ref -->
    <button class="hide-on-drawer-visible" @click="$refs.rightDrawer.open()">
        <i>menu</i>
      </button>
  </div>
  <!-- Navigation Tabs -->
  <q-tabs slot="navigation">
    <q-tab icon="mail" route="/layout" exact replace>Mails</q-tab>
    <q-tab icon="alarm" route="/layout/alarm" exact replace>Alarms</q-tab>
    <q-tab icon="help" route="/layout/help" exact replace>Help</q-tab>
  </q-tabs>
  <!-- Left-side Drawer -->
  <q-drawer ref="leftDrawer">
    <div class="toolbar">
      <q-toolbar-title>
        Drawer Title
      </q-toolbar-title>
    </div>
    <div class="list no-border platform-delimiter">
      <q-drawer-link icon="mail" :to="{path: '/', exact: true}">
        Link
      </q-drawer-link>
    </div>
  </q-drawer>
  <!-- IF USING subRoutes only: -->
  <router-view class="layout-view"></router-view>
  <!-- OR ELSE, IF NOT USING subRoutes: -->
 <div class="layout-view">
   Hello:   <input v-model="title">
   <button class="raised circular yellow" @click="add(title)" :disabled="title==''" ><i>send</i></button>
   <ul  v-for="todo in todos" :key="todo">
    <li>
        {{todo.task}} - {{todo.user}} <span @click="remove(todo)" style="color: red"><i>delete</i></span>
        
     </li>

   </ul>
  </div>
  <!-- Right-side Drawer -->
  <q-drawer ref="rightDrawer" right-side>
    ...
  </q-drawer>
  <!-- Footer -->
  <div slot="footer" class="toolbar">
    ....
  </div>
</q-layout>
    
</template>

<script>
import _ from 'lodash'
export default {
  data () {
      return{ 
        title: 'Hello batch 7',
        todos: []
  }
},
methods: {
    add (ttl) {
        let todo = {
            user: 'Pogi',
            task: ttl
        }
        this.todos.push(todo)
        this.title = ''
    },
    remove (ttl) {
        let index = _.indexOf(this.todos, ttl)
        this.todos.splice(index, 1)
    }
    
}
}
</script>
