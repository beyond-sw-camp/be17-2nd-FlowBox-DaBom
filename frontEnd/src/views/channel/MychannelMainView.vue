<script>
  import Sidebar from '@/components/channel/MyChannelSidbar.vue';
  import VideoSection from '@/components/channel/VideoSection.vue';
  import PlaylistSection from '@/components/channel/PlaylistSection.vue';
  import CommunitySection from '@/components/channel/CommunitySection.vue';
  import InfoSection from '@/components/channel/InfoSection.vue';
  
  export default {
    name: 'MyChannel',
    components: {
      Sidebar,
      VideoSection,
      PlaylistSection,
      CommunitySection,
      InfoSection
    },
    data() {
      return {
        currentSection: 'videos'
      };
    },
    methods: {
      handleNavigation(section) {
        this.currentSection = section;
      }
    }
  }
  </script>
<template>
    <div class="channel-dashboard">
      <Sidebar :currentSection="currentSection" @navigate="handleNavigation" />
      <main class="dashboard-main">
        <VideoSection :isActive="currentSection === 'videos'" />
        <PlaylistSection :isActive="currentSection === 'playlists'" />
        <CommunitySection :isActive="currentSection === 'community'" />
        <InfoSection :isActive="currentSection === 'info'" />
      </main>
    </div>
  </template>
  
  
  
  <style scoped>
  @import url(@/assets/channel/mychannel);
  </style>