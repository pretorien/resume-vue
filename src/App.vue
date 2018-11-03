<template>
  <div id="app">
      <div v-if="!userProfile">Chargement des données en cours</div>
      <div v-else>
          <GithubRibbon :url="project_url" :label="project_label"></GithubRibbon>
          <Header :name="userProfile.name" :poste="userProfile.poste" :city="userProfile.city" :email="userProfile.email" :social="userProfile.social" :other="userProfile.other" />
          <div class="page-content">
              <div class="wrapper">
                  <div class="container-fluid">
                      <div class="row" style="display: flex">
                          <div class="col-md-7">
                              <JobHistory :jobs="userProfile.jobs" />
                              <EducationHistory :degrees="userProfile.degrees" />
                              <ProfessionalTraining :courses="userProfile.courses" />
                          </div>
                          <div class="col-md-4 offset-md-1">
                              <SkillsList :skills="userProfile.skills" />
                              <div class="deviter"></div>
                              <Languages :languages="userProfile.languages" />
                              <!--<div class="deviter"></div>-->
                              <!--<Location :location="userProfile.location" />-->
                          </div>
                      </div>
                  </div>
              </div>
          </div>
          <Footer />
      </div>
  </div>
</template>

<script>

    import Header from '@/components/Header.vue'
    import JobHistory from "@/components/JobHistory";
    import SkillsList from "@/components/SkillsList";
    import Footer from "@/components/Footer";
    import EducationHistory from "@/components/EducationHistory";
    import Location from "@/components/Location";
    import Languages from "@/components/Languages";
    import ProfessionalTraining from "@/components/ProfessionalTraining";

    import userProfile from "@/static/data/cv.json";
    import GithubRibbon from "./components/GithubRibbon";

    export default {
        name: 'app',
        components: {
            GithubRibbon,
            ProfessionalTraining,
            Languages,
            Location,
            EducationHistory,
            Footer,
            SkillsList,
            JobHistory,
            Header
        },
        data() {
            return {
                userProfile,
                project_url: 'https://github.com/pretorien/cv-vue',
                project_label: 'cv-vue'
            }
        },
        created () {
            document.title = 'CV - ' + this.userProfile.name;
        }
    }

</script>


<style>
    @import './assets/css/resumecard.css';
</style>

<style lang="scss">
    @import '../node_modules/bootstrap/scss/bootstrap.scss';
</style>
