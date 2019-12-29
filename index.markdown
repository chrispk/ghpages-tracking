---
layout: page
---
<h1>Opt-in/opt-out of tracking on {{ site.url | remove:'http://' | remove:'https://' | remove:'tracking.' | split:'/' | first }}</h1>

<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="inputDisableTracking">
  <label class="form-check-label" for="defaultCheck1">
    Disable tracking on <strong>{{ site.url | remove:'http://' | remove:'https://' | remove:'tracking.' | split:'/' | first }}</strong> indefinitely for this browser session
  </label>
</div>

<script type="text/javascript">
  function onload(){
    var inputDisableTracking = document.getElementById("inputDisableTracking");
    console.log("test");
    inputDisableTracking.checked = true;
  }
  window.onload = onload();

  // enableTracking() {

  // }

  // disableTracking() {
    
  // }
</script>