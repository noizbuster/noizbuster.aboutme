<template>
  <v-container>
    <v-layout wrap>

      <!--title-->
      <v-flex xs12 pl-2 pb-4 class="font-weight-regular display-3 primary--text">Projects</v-flex>

      <v-flex xs12 pl-2 pb-3 class="font-weight-regular display-2 primary--text">Company Projects</v-flex>
      <!--projects-->
      <v-flex xs12>
        <project-view
          v-for="(project, cpi) in myProjects.company_projects" :key="cpi"
          :project="project"
        ></project-view>
      </v-flex>

      <v-flex xs12 pl-2 pb-3 pt-5 class="font-weight-regular display-2 primary--text">Personal Projects</v-flex>
      <v-flex xs12>
        <project-view
          v-for="(project, ppi) in myProjects.personal_projects" :key="ppi"
          :project="project"
        ></project-view>
      </v-flex>

    </v-layout>
  </v-container>
</template>

<script>
  import SkillBadge from '~/components/SkillBadge.vue'
  import TagBadge from '~/components/TagBadge.vue'
  import SkillItem from '~/components/SkillItems.vue'
  import SkillList from '~/components/SkillList.vue'
  import myProjects from '~/assets/projects'
  import mySkills from '~/assets/skills'
  import ProjectView from '~/components/ProjectView.vue'

  export default {
    components: {
      SkillBadge,
      TagBadge,
      SkillItem,
      SkillList,
      ProjectView
    },
    data() {
      return {
        myProjects,
        mySkills
      }
    }
  }
</script>
