---
layout: form
title: Reimburesement
permalink: /reimbursement/
---
<div id="surveyContainer"></div>

<script type="text/javascript">

Survey.Survey.cssType = "bootstrap";

var surveyJSON = { surveyId: 'fa7c2809-a428-4311-b8f0-591d8fdf6cc5'}

function sendDataToServer(survey) {
    survey.sendResult('a4967044-202c-45f7-b055-072a93642a8c');
}

var survey = new Survey.Model(surveyJSON, "surveyContainer");
survey.onComplete.add(sendDataToServer);





</script>
