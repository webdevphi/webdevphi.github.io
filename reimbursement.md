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
survey.onComplete.add(function (sender, options) {
    //Show message about "Saving..." the results
    options.showDataSaving();//you may pass a text parameter to show your own text
    var data = new FormData();
    data.append( "json", JSON.stringify(sender.data) );
    fetch("https://script.google.com/a/mylaurier.ca/macros/s/AKfycbz0GWAcZ44kwQ27ZZ3WZGzhG2U4Y18u9HhgQfC-8C8/dev",
    {
        method: "POST",
        body: data
    }).then(function(res){ return res.json(); }).then(function(data){ options.showDataSavingSuccess() })
});





</script>
