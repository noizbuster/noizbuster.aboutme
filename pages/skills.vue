<template>
  <v-container>
    <v-layout wrap>

      <!--title-->
      <v-flex pl-2 class="primary--text font-weight-regular display-3">Tech. Skills</v-flex>
      <!--legend-->
      <v-flex xs12 pa-2 class="font-weight-bold">
        <v-card>
          <v-card-title>
            <div>
              <SkillBadge level="expert"></SkillBadge>
              Expert: I am not only able to use this technique, but also have a deep understanding of it.
            </div>
            <div>
              <SkillBadge level="skilled"></SkillBadge>
              Working Knowledge: I have worked with and feel comfortable using. and ready to use them in practical work.
            </div>
            <div>
              <SkillBadge level="basic"></SkillBadge>
              Basic Knowledge: I have played with or have a basic understanding of their purpose.
            </div>
          </v-card-title>
        </v-card>
      </v-flex>

      <v-flex xs12 mt-5 pa-2 class="font-weight-bold">
        <v-checkbox v-for="i in tagFilters" :key="'tagFilter'+i" v-model="tag" :label="i.label"
                    :value="i.value"></v-checkbox>
      </v-flex>


      <v-flex xs12 mt-5 pa-2 class="font-weight-bold">
        <div class="primary--text font-weight-regular display-1">Back-End</div>
        <skill-list :skills="skills"></skill-list>
      </v-flex>

      <v-flex xs12 mt-5 pa-2 class="font-weight-bold">
        <div class="primary--text font-weight-regular display-1">Front-End</div>
        <skill-list :skills="skills_frontend"></skill-list>
      </v-flex>

      <v-flex xs12 mt-5 pa-2 class="font-weight-bold">
        <div class="primary--text font-weight-regular display-1">Computer Languages</div>
        <skill-list :skills="skills_planguage"></skill-list>
      </v-flex>

      <v-flex xs12 mt-5 pa-2 class="font-weight-bold">
        <div class="primary--text font-weight-regular display-1">ETC</div>
        <skill-list :skills="skills_etc"></skill-list>
      </v-flex>

      <!--title-->
      <v-flex pl-2 mt-5 class="primary--text font-weight-regular display-3">Skills</v-flex>

      <v-flex xs12 pa-2 class="font-weight-bold">
        <div class="primary--text font-weight-regular display-1">Spoken Languages</div>
        <skill-list :skills="skills_hlanguage"></skill-list>
      </v-flex>

    </v-layout>
  </v-container>
</template>

<script>
  import SkillBadge from '~/components/SkillBadge.vue'
  import TagBadge from '~/components/TagBadge.vue'
  import SkillItem from '~/components/SkillItems.vue'
  import SkillList from '~/components/SkillList.vue'
  import mySkills from '~/assets/skills'

  const tagFilters = mySkills.tagFilters;
  // const tags_values = _.reduce(tagFilter, (result, value, key)=>{
  //   return result.push(value.value);
  // }, []);
  export default {
    components: {
      SkillBadge,
      TagBadge,
      SkillItem,
      SkillList
    },
    data() {
      return {
        skills: _.filter(mySkills.skills, {tag: 'backend'}),
        tag_selected: []
      }
    }
  }
</script>
