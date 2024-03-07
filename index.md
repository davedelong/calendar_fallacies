<div class="fallacy-list">
{% for fallacy in site.data.fallacies %}
  {% assign id = "" %}
  {% if fallacy.id.size > 0 %}
   {% assign id = fallacy.id %}
  {% else %}
   {% assign id = fallacy.name | slugify %}
  {% endif %}
  
  {% assign title = fallacy.name | markdownify | remove_first: "<p>" %}
  {% assign reversedTitle = title | split: "" | reverse | join: "" | remove_first: ">p/<" %}
  {% assign title = reversedTitle | split: "" | reverse | join: "" %}
  
  <div class="fallacy" id="{{ id }}">
    <h2>
    {{ title }}
    <a href="#{{ id }}">
    	<svg viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true">
    	  <path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path>
    	</svg>
    </a>
    </h2>
    <div class="explanation">{{ fallacy.body | markdownify }}</div>
    
    {% if fallacy.tags.size > 0 %}
      <div class="tags">
      {% for tag in fallacy.tags %}
        <div class="tag">{{ tag }}</div>
      {% endfor %}
      </div>
    {% endif %}
  </div>
{% endfor %}
</div>

<script>
const timestamps = document.getElementsByTagName("timestamp");
var requests = [];

for (var i = 0; i < timestamps.length; i++) {
	var tag = timestamps[i];
	tag.id = "timestamp-"+i;
	
	var request = { 'id': tag.id };
	request.locale = 'en_US';
	
	if (tag.hasAttribute('calendar')) {
		request.calendar = tag.getAttribute('calendar');
	}
	
	if (tag.hasAttribute('template')) {
		request.format = { 'template': tag.getAttribute('template') };
	}
	
	requests.push(request);
}

/*
	This updates the localized timestamps on the page by using the API for nsdateformatter.com
*/
const formatEndpoint = "https://api.nsdateformatter.com/api/format";

fetch(formatEndpoint, {
  method: "POST",
  body: JSON.stringify(requests),
  headers: {
    "Content-type": "application/json; charset=UTF-8"
  }
})
.then((response) => response.json())
.then(function (json) {
	for (var i = 0; i < json.length; i++) {
		var tag = document.getElementById(json[i].id);
		var text = document.createTextNode(json[i].value);
		tag.appendChild(text);
	}
});


/*
	This creates the information about how many tzdb changes have happened recently.
	It works by counting the number of tags on the eggert/tz git repo, which correlate to
	the tzdb releases. It then buckets them by year and picks the two most recent years of
	changes in order to build a summary to show on the page.
*/
fetch("https://api.github.com/repos/eggert/tz/git/refs/tags")
	.then((response) => response.json())
	.then(function (json) {
		var yearBuckets = {};
		for (var i = 0; i < json.length; i++) {
			var ref = json[i].ref;
			var releaseName = ref.replace(/^refs\/tags\//, '');
			var year = releaseName.substr(0, 4);
			
			if (yearBuckets[year] === undefined) {
				yearBuckets[year] = [];
			}
			yearBuckets[year].push(releaseName);
		}
		
		var tzSummary = document.getElementById("tzchanges");
		var currentYear = new Date().getFullYear();
		
		var tzchanges = "";
		
		var summaryCounts = 0;
		for (var year = currentYear; year >= 2012 && summaryCounts < 2; year--) {
			var isCurrentYear = (year == currentYear);
			if (yearBuckets[year] !== undefined && yearBuckets[year].length > 0) {
				var prefix = "In ";
				
				var count = yearBuckets[year].length;
				var verb = (count == 1) ? "was" : "were";
				if (isCurrentYear) {
					verb = (count == 1) ? "has been" : "have been";
					prefix = "So far in ";
				}
				var changes = (count == 1) ? "change" : "changes"
				
				var suffix = " to the time zone database"
				if (summaryCounts > 0) { 
					tzchanges += " "; 
					suffix = "";
				}
				
				tzchanges += prefix + year + " there " + verb + " " + count + " " + changes + suffix + ".";
				summaryCounts += 1;
			}
		}
		
		var tzChangeNode = document.createTextNode(tzchanges);
		tzSummary.appendChild(tzChangeNode);
	});
</script>

