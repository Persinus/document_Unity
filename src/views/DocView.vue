<template>
  <div class="doc-view">
    <div class="sidebar">
      <div class="sidebar-header">
      </div>
      <Sidebar @topic-selected="loadContent" />
    </div>
    <div class="content">
      <va-card class="content-card" outlined>
        <div class="content-header">
          <h2>
            <span class="gradient-text">{{ currentComponent.replace(/([A-Z])/g, ' $1').trim() }}</span>
          </h2>
        </div>
        <component :is="currentComponent" />
      </va-card>
    </div>
  </div>
</template>

<script>
import { VaCard } from 'vuestic-ui';
import Sidebar from '@/components/Sidebar.vue';
import GettingStarted from '@/components/GettingStarted.vue';
import CoreConcepts from '@/components/CoreConcepts.vue';
import Essentials from '@/components/Essentials.vue';
import ThemeUnity from '@/components/ThemeUnity.vue';

export default {
  components: {
    Sidebar,
    GettingStarted,
    CoreConcepts,
    Essentials,
    ThemeUnity,
    VaCard,
  },
  data() {
    return {
      currentComponent: 'GettingStarted',
    };
  },
  methods: {
    loadContent(topic) {
      this.currentComponent = topic;
    },
  },
};
</script>

<style scoped>
.doc-view {
  display: flex;
  min-height: 100vh;
}



.sidebar-header {

  display: flex;
  align-items: center;

  border-bottom: 1px solid #ffffff;
}





.content {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding: 48px 0;
}

.content-card {
  width: 100%;
  max-width: 900px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.18);
  background: #23272f;
  color: #fff;
  border-radius: 24px;
  padding: 40px 40px 32px 40px;
  border: none;
  position: relative;
  transition: box-shadow 0.2s;
}

.content-card:hover {
  box-shadow: 0 12px 48px rgba(0, 0, 0, 0.22);
}

.content-header {
  margin-bottom: 24px;
  border-bottom: 1px solid #333;
}

.gradient-text {
  background: linear-gradient(90deg, #00c3ff 0%, #ffff1c 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: 700;
  font-size: 2rem;
  letter-spacing: 1px;
}
</style>
