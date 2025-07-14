<template>
  <aside class="sidebar">
    <h1 class="logo">Unity<span>Docs</span></h1>
    <nav>
      <SidebarList :items="topics" :selected="selected" :subSelected="subSelected" @select="handleSelect" />
    </nav>
  </aside>
</template>

<script>
import SidebarList from './SidebarList.vue';

export default {
  components: { SidebarList },
  data() {
    return {
      selected: 'GettingStarted',
      subSelected: '',
      topics: [
        { key: 'GettingStarted', label: 'Getting Started', icon: '📘' },
        {
          key: 'DesignPattern', label: 'Design Pattern', icon: '🧩',
          children: [
            { key: 'Singleton', label: 'Singleton', icon: '🔑' },
            { key: 'Multiton', label: 'Multiton', icon: '🔗' },
            { key: 'Observer', label: 'Observer', icon: '👀' },
            { key: 'Factory', label: 'Factory', icon: '🏭' },
            { key: 'Strategy', label: 'Strategy', icon: '🎯' },
            { key: 'Command', label: 'Command', icon: '📜' },
            {key: 'Decorator', label: 'Decorator', icon: '🎨' },
            { key: 'Prototype', label: 'Prototype', icon: '🖼️' },
            { key: 'Adapter', label: 'Adapter', icon: '🔌' },
            { key: 'Facade', label: 'Facade', icon: '🏛️' },
            { key: 'Bridge', label: 'Bridge', icon: '🌉' },
            { key: 'Composite', label: 'Composite', icon: '🧱' },
            { key: 'Builder', label: 'Builder', icon: '🛠️' },
            { key: 'ChainOfResponsibility', label: 'Chain of Responsibility', icon: '🔗' },
            { key: 'State', label: 'State', icon: '🏷️' },
            { key: 'Visitor', label: 'Visitor', icon: '👥' },
            { key: 'Memento', label: 'Memento', icon: '🗃️' },
            { key: 'Prototype', label: 'Prototype', icon: '🖼️'},
            { key: 'LazyInitialization', label: 'Lazy Initialization', icon: '⏳' },
            { key: 'ObjectPool', label: 'Object Pool', icon: '🏊' },
            { key: 'ServiceLocator', label: 'Service Locator', icon: '🔍' },
            { key: 'DependencyInjection', label: 'Dependency Injection', icon: '🔗' },
            {key : 'Object Mother', label: 'Object Mother', icon: '👶' },
            { key: 'Repository', label: 'Repository', icon: '📚' },
            { key: 'UnitOfWork', label: 'Unit of Work', icon: '🛠️' }

          ]
        },
        { key: 'Emergent', label: 'Emergent', icon: '🌱' },
        { key: 'Optimization', label: 'Optimization', icon: '⚡' },
        { key: 'Cloud', label: 'Cloud', icon: '☁️' },
        { key: 'Testing', label: 'Testing', icon: '🧪' },
        { key: 'Concurrent', label: 'Concurrent', icon: '🔀' },
        { key: 'Security', label: 'Security', icon: '🔒' },
        { key: 'DataAccess', label: 'Data Access', icon: '💾' },
        { key: 'Architectural', label: 'Architectural', icon: '🏛️' },
        { key: 'Behavioural', label: 'Behavioural', icon: '🤖' },
        { key: 'Essentials', label: 'Essentials', icon: '🧰' },
        { key: 'ThemeUnity', label: 'Theme Unity', icon: '🎮' }
      ]
    };
  },
  methods: {
    handleSelect(topic) {
      this.selected = topic;
      this.subSelected = '';
      this.$emit('topic-selected', topic);
    }
  }
};
</script>

<style scoped>
.sidebar {
  width: 250px;
  background: linear-gradient(120deg, #23272f 60%, #181818 100%);
  padding: 32px 20px 20px 20px;
  border-right: 1px solid #2c313a;
  color: #fff;
  min-height: 100vh;
  box-shadow: 2px 0 16px rgba(0, 0, 0, 0.10);
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  font-family: 'Segoe UI', 'Roboto', Arial, sans-serif;
}

.logo {
  font-size: 24px;
  font-weight: bold;
  color: #38bdf8;
  margin-bottom: 40px;
}

.logo span {
  color: #f1f5f9;
}

nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
  width: 100%;
}

nav li {
  margin-bottom: 8px;
}

.parent-item {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  border-radius: 8px;
  cursor: pointer;
  transition: background 0.3s, color 0.3s, box-shadow 0.2s;
  color: #fff;
  font-size: 1rem;
  font-weight: 500;
  letter-spacing: 0.5px;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.04);
  position: relative;
}

.parent-item:hover,
nav li.active .parent-item {
  background: linear-gradient(90deg, #00c3ff55 0%, #ffff1c55 100%);
  color: #23272f;
  font-weight: bold;
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.12);
}

.arrow {
  margin-left: auto;
  font-size: 14px;
  color: #00c3ff;
}

.submenu {
  margin-top: 4px;
  margin-left: 12px;
  padding-left: 8px;
  border-left: 2px solid #00c3ff44;
}

.submenu li {
  display: flex;
  align-items: center;
  padding: 8px 12px;
  border-radius: 6px;
  cursor: pointer;
  font-size: 0.98rem;
  color: #fff;
  margin-bottom: 2px;
  transition: background 0.2s, color 0.2s;
}

.submenu li.subactive,
.submenu li:hover {
  background: linear-gradient(90deg, #00c3ff33 0%, #ffff1c33 100%);
  color: #23272f;
  font-weight: bold;
}

.icon,
.subicon {
  font-size: 18px;
  margin-right: 10px;
}

.label,
.sublabel {
  flex: 1;
}
</style>
