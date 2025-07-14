<template>
  <div class="singleton-pattern">
    <h2>Singleton Pattern in Unity</h2>
    <p>
      The Singleton pattern ensures a class has only one instance and provides a global point of access to it.
      In Unity, this is commonly used for managers (GameManager, AudioManager, etc).
    </p>
    <va-card color="info" class="code-card" outlined>
      <pre><code>{{ code }}</code></pre>
    </va-card>
    <ul>
      <li>Only one instance exists during runtime.</li>
      <li>Access via <code>Instance</code> property.</li>
      <li>Useful for global managers.</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'SingletonPattern',
  data() {
    return {
      code: `public class GameManager : MonoBehaviour {
  public static GameManager Instance { get; private set; }
  void Awake() {
    if (Instance == null) {
      Instance = this;
      DontDestroyOnLoad(gameObject);
    } else {
      Destroy(gameObject);
    }
  }
}`
    }
  }
}
</script>

<style scoped>
.singleton-pattern {
  padding: 16px;
}

.code-card {
  margin: 16px 0;
  font-size: 0.95rem;
  background: #181818;
  color: #00c3ff;
  border-radius: 8px;
}
</style>
