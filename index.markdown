---
layout: page
---
<h1>Opt-in/opt-out of tracking on {{ site.url | remove:'http://' | remove:'https://' | remove:'tracking.' | split:'/' | first }}</h1>

<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="checkboxDisableTracking">
  <label class="form-check-label" for="defaultCheck1">
    Disable tracking on <strong>{{ site.url | remove:'http://' | remove:'https://' | remove:'tracking.' | split:'/' | first }}</strong>  for this browser session
  </label>
</div>

<script type="text/javascript">
	function setInternalUserCookie(yearsExpires) {
		var date = new Date();
		date.setFullYear(date.getFullYear() + yearsExpires);
		var apexDomain = window.location.hostname.replace("tracking.", "");
		document.cookie = "internalUser=true; expires=" + date.toUTCString() +"; path=/;domain=" + apexDomain;
		return true;
	}
	function onload(){
		var checkboxDisableTracking = document.getElementById("checkboxDisableTracking");
		checkboxDisableTracking.checked = setInternalUserCookie(50); // set cookie with 50 year expiry date
		checkboxDisableTracking.addEventListener( 'change', function() {
		    if(this.checked) {
		        setInternalUserCookie(50); // set cookie with 50 year expiry date
		    } else {
		        setInternalUserCookie(-1); // set cookie with past expiry date (i.e. remove cookie)
		    }
		});
	}
	window.onload = onload();
</script>