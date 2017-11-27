<template>
<footer class="footer">
  <div class="container">
    <div class="content has-text-centered">
      <p>
        {{ person.fields.name }} made this site. You can find him here on <a :href="person.fields.github">Github</a>
      </p>
    </div>
  </div>
</footer>
</template>
