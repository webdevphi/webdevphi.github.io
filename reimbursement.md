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
    var xhr = new XMLHttpRequest();
    xhr.open("POST", "https://script.google.com/a/mylaurier.ca/macros/s/AKfycbz0GWAcZ44kwQ27ZZ3WZGzhG2U4Y18u9HhgQfC-8C8/dev");
    xhr.setRequestHeader("Content-Type", "application/json; charset=utf-8");
    xhr.onload = xhr.onerror = function () {
        if (xhr.status == 200) {
            options.showDataSavingSuccess(); //you may pass a text parameter to show your own text
            //Or you may clear all messages
            //options.showDataSavingClear();
        } else {
            //Error
            options.showDataSavingError(); //you may pass a text parameter to show your own text
        }
    };
    xhr.send(JSON.stringify(sender.data));
});





</script>
