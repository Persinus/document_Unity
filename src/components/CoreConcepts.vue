<template>
  <div class="core-concepts">
    <h1>Core Concepts of Unity</h1>
    <p>Unity is a powerful game development platform that allows developers to create 2D and 3D games. Here are some of
      the core concepts you should understand:</p>
    <ul>
      <li><strong>GameObjects:</strong> The fundamental objects in Unity that represent characters, props, scenery, and
        more.</li>
      <li><strong>Components:</strong> The building blocks of GameObjects that define their behavior and functionality.
      </li>
      <li><strong>Scenes:</strong> The environments where your GameObjects exist, which can be loaded and unloaded as
        needed.</li>
      <li><strong>Assets:</strong> Files such as textures, models, and audio that are used in your game.</li>
      <li><strong>Scripting:</strong> The process of writing code to control the behavior of GameObjects and implement
        game logic.</li>
    </ul>
    <p>Understanding these concepts is essential for effective game development in Unity.</p>
  </div>
</template>

<script>
export default {
  name: 'CoreConcepts',
};
</script>

<style scoped>
.core-concepts {
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
}

.core-concepts h1 {
  color: #333;
}

.core-concepts p {
  color: #555;
}

.core-concepts ul {
  list-style-type: disc;
  margin-left: 20px;
}

.core-concepts li {
  margin: 5px 0;
}
</style>
