<template>
  <div class="dashboard">
    <h1 class="subheading grey--text">Dashboard</h1>
    
    <v-conteiner> 
      <v-card class="ps-12 pr-12 ms-12 mr-12" flat v-for="project in projects" :key="project.title">
        <v-row :class="`pa-3 ps-3 project ${project.status} `">
          <v-col col="12" md="6">
            <div class="caption grey--text">Project title</div>
            <div>{{project.title}}</div>
          </v-col>
          <v-col col="6" sm="4" md="2">
            <div class="caption grey--text">Person</div>
            <div>{{project.person}}</div>
          </v-col>
          <v-col col="6" sm="4" md="2">
            <div class="caption grey--text">Due by</div>
            <div>{{project.due}}</div>
          </v-col>
          <v-col col="2" sm="4" md="2">
            <div class="rigth">
              <v-chip small :class="`${project.status} white--text caption my-2`" id="v-chipDashboard" >{{project.status}}</v-chip>
            </div>
          </v-col>
        </v-row>
      </v-card>
    </v-conteiner>

  </div>
 
</template>

<script>


export default {
	data () {
		return{
      alignment: 'center',
      projects: [
        { title: 'Design a new website', person: 'The Net Ninja', due: '1st Jan 2019', status: 'ongoing', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Code up the homepage', person: 'Chun Li', due: '10th Jan 2019', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Design video thumbnails', person: 'Ryu', due: '20th Dec 2018', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
        { title: 'Create a community forum', person: 'Gouken', due: '20th Oct 2018', status: 'overdue', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'},
      ]
		}
	},
}
</script>
<style>
  .project.complete{
    border-left: 4px solid #3cd1c2;
  }
  .project.ongoing{
     border-left: 4px solid orange;
  }
  .project.overdue{
     border-left: 4px solid tomato;
  }
  #v-chipDashboard.complete{
    background: #3cd1c2;
  }
  #v-chipDashboard.ongoing{
     background: orange;
  }
  #v-chipDashboard.overdue{
     background: tomato;
  }
</style>