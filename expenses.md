---
layout: form
title: Expense Form
permalink: /expenses
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
    console.log(sender.data)
    $.ajax({
      type: 'POST',
      url: "https://script.google.com/macros/s/AKfycbwM1uSHvNl7BxnzWqK-0lBYpGyNrMQIZR_8CPkQVPulSTdgjvI/exec",
      data: JSON.stringify(sender.data),
      complete: (data) => {
        console.log(data);
        options.showDataSavingSuccess();
      },
      dataType: "json"
    });
});





</script>
