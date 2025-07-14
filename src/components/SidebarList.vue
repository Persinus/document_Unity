<template>
  <ul>
    <li v-for="item in items" :key="item.key">
      <div class="parent-item" :class="{ expanded: expandedKey === item.key }" @click="handleParentClick(item)">
        <span class="icon">{{ item.icon }}</span>
        <span class="label">{{ item.label }}</span>
        <span v-if="item.children" class="arrow">
          {{ expandedKey === item.key ? '▲' : '▼' }}
        </span>
      </div>
      <ul v-if="item.children && expandedKey === item.key" class="submenu">
        <li v-for="sub in item.children" :key="sub.key" class="child-item" @click.stop="handleChildClick(sub)">
          <span class="icon">{{ sub.icon }}</span>
          <span class="label">{{ sub.label }}</span>
        </li>
      </ul>
      <SidebarList v-if="item.children && Array.isArray(item.children[0]?.children)" :items="item.children"
        @select="$emit('select', $event)" />
    </li>
  </ul>
</template>

<script>
export default {
  name: 'SidebarList',
  props: {
    items: Array
  },
  data() {
    return {
      expandedKey: null
    }
  },
  methods: {
    handleParentClick(item) {
      if (item.children) {
        this.expandedKey = this.expandedKey === item.key ? null : item.key;
      } else {
        this.$emit('select', item.key);
      }
    },
    handleChildClick(sub) {
      this.$emit('select', sub.key);
    }
  }
};
</script>

<style scoped>
.parent-item {
  display: flex;
  align-items: center;
  padding: 8px 12px;
  border-radius: 8px;
  cursor: pointer;
  transition: background 0.3s, color 0.3s;
  color: #fff;
  font-size: 1rem;
  font-weight: 500;
  margin-bottom: 4px;
}

.parent-item:hover,
.parent-item.expanded {
  background: linear-gradient(90deg, #00c3ff33 0%, #ffff1c33 100%);
  color: #23272f;
}

.icon {
  font-size: 18px;
  margin-right: 10px;
}

.label {
  flex: 1;
}

.arrow {
  margin-left: auto;
  font-size: 14px;
  color: #00c3ff;
}

.submenu {
  margin-left: 18px;
  margin-top: 2px;
  padding-left: 8px;
  border-left: 2px solid #00c3ff44;
}

.child-item {
  display: flex;
  align-items: center;
  padding: 7px 10px;
  border-radius: 6px;
  cursor: pointer;
  font-size: 0.98rem;
  color: #fff;
  margin-bottom: 2px;
  transition: background 0.2s, color 0.2s;
}

.child-item:hover {
  background: linear-gradient(90deg, #00c3ff33 0%, #ffff1c33 100%);
  color: #23272f;
  font-weight: bold;
}
</style>
