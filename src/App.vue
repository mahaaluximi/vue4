<template>
  <div>
    <!-- <the-header></the-header>
    <badge-list></badge-list> -->
   
    <TheHeader/>
    <button @click="setSelectedComponent('ActiveGoals')">Active Goals</button>
    <button @click="setSelectedComponent('ManageGoals')">Manage Goals</button>
    <!-- conditionally rendering the components based on the selected component -->
    <!-- The below conditional rendering is done is cumbersome so vue has given <component> tag -->
    <!-- <ActiveGoals v-if="selectedComponent === 'ActiveGoals'"/>
    <ManageGoals v-if="selectedComponent === 'ManageGoals'"></ManageGoals> -->
    <!-- <component v-bind:is="selectedComponent"></component> -->
    <!-- shorthand notation -->
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
    
    <!-- <BadgeList/>
    <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>
    <course-goals v-slot:default="slotProps"> -->
      <!-- Here v-slot:default is given as it is the default slot and 
      slotProps (can be any name) is used to access the data passed to the default slot -->
      <!-- <template v-slot:default="slotProps"> -->
        <!-- <h2>{{ slotProps.item }}</h2>
        <p>{{ slotProps.addnInfo }}</p> -->
      <!-- </template> -->
    <!-- </course-goals> -->
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
// import BadgeList from './components/BadgeList.vue';
// import UserInfo from './components/UserInfo.vue';
// import CourseGoals from './components/CourseGoals.vue';
import ActiveGoals from './components/ActiveGoals.vue';
import ManageGoals from './components/ManageGoals.vue';
export default {
  components: {
    TheHeader,
    // BadgeList,
    // UserInfo,
    // CourseGoals,
    ActiveGoals,
    ManageGoals
  },
  data() {
    return {
      selectedComponent: 'ActiveGoals',
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selectedComponent = cmp;
      console.log('selected:',this.selectedComponent);
    },  
    
  }
};
</script>

<style >
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>