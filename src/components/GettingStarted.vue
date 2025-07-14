<template>
  <div class="getting-started">
    <h1>Getting Started with Unity</h1>
    <p>Welcome to the Unity documentation! This section will guide you through the basics of getting started with Unity.</p>

    <h2>Installation</h2>
    <p>To begin, you need to install the Unity Hub, which will help you manage your Unity installations and projects.</p>

    <h2>Creating Your First Project</h2>
    <p>Once you have Unity installed, you can create your first project by following these steps:</p>
    <ol>
      <li>Open Unity Hub.</li>
      <li>Click on the 'New' button.</li>
      <li>Select a template (2D, 3D, etc.) and name your project.</li>
      <li>Choose a location to save your project and click 'Create'.</li>
    </ol>

    <h2>Understanding the Interface</h2>
    <p>The Unity interface consists of several panels, including the Scene view, Game view, and Inspector. Familiarize yourself with these panels to navigate your project effectively.</p>

    <h2>First Steps in Unity</h2>
    <p>Start by adding GameObjects to your scene. You can do this by right-clicking in the Hierarchy panel and selecting '3D Object' or '2D Object'.</p>

    <h2>Resources</h2>
    <p>For more detailed instructions, check out the official Unity documentation and tutorials available on the Unity website.</p>
  </div>
</template>

<script>
export default {
  name: 'GettingStarted'
}
</script>

<style scoped>
.getting-started {
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
}
.getting-started h1 {
  color: #333;
}
.getting-started h2 {
  color: #555;
}
.getting-started p {
  color: #666;
}
.getting-started ol {
  margin-left: 20px;
}
</style>
