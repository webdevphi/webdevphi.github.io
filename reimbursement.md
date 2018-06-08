---
layout: form
title: Reimburesement
permalink: /reimbursement/
---
<div id="surveyContainer"></div>

<script type="text/javascript">

Survey.Survey.cssType = "bootstrap";

function sendDataToServer(survey) {
    //send Ajax request to your web server.
    console.log(survey)
}

$.getJSON("{{ site.baseurl }}/form.json", function(json){
    var survey = new Survey.Model(json);
    $("#surveyContainer").Survey({
        model: survey,
        onComplete: sendDataToServer
    });
});





</script>
