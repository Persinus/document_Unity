
<template>
  <div class="essentials">
    <h1>Unity Essentials</h1>
    <p>Welcome to the Unity Essentials section. Here you will find the fundamental concepts and tools necessary to get started with Unity development.</p>
    <h2>Key Topics</h2>
    <ul>
      <li>Understanding the Unity Interface</li>
      <li>Creating Your First Project</li>
      <li>Basic Scripting in C#</li>
      <li>Working with Game Objects</li>
      <li>Introduction to Physics and Animation</li>
    </ul>
    <h2>Resources</h2>
    <p>For more detailed information, check out the following resources:</p>
    <ul>
      <li><a href="https://unity.com/learn">Unity Learn</a></li>
      <li><a href="https://docs.unity3d.com/Manual/index.html">Unity Manual</a></li>
      <li><a href="https://forum.unity.com/">Unity Forum</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'EssentialsSection',
};
</script>

<style scoped>
.essentials {
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
}
h1 {
  color: #333;
}
h2 {
  color: #555;
}
ul {
  list-style-type: disc;
  margin-left: 20px;
}
a {
  color: #007bff;
  text-decoration: none;
}
a:hover {
  text-decoration: underline;
}
</style>
