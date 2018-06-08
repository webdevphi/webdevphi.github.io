---
layout:form
title: Reimburesement
permalink: /reimbursement/
---
<div id="surveyContainer"></div>

<script type="text/javascript">

Survey.Survey.cssType = "bootstrap";

var surveyJSON = {pages:[{name:"page1",elements:[{type:"panel",name:"etransfer-info",elements:[{type:"text",name:"etransfer-payee",title:"Payee",isRequired:true},{type:"text",name:"etransfer-email",title:"Email",isRequired:true}],title:"E-Transfer Info"},{type:"paneldynamic",name:"receipt-info",title:"Receipts",templateElements:[{type:"text",name:"receipt-date",title:"Date",isRequired:true,inputType:"datetime"},{type:"text",name:"receipt-description",title:"Description",isRequired:true},{type:"text",name:"receipt-amount",title:"Amount",isRequired:true,inputType:"number"},{type:"file",name:"receipt-image",title:"Image",isRequired:true,maxSize:0}],panelCount:1,minPanelCount:1,confirmDelete:true}]}]}

function sendDataToServer(survey) {
    //send Ajax request to your web server.
    console.log(survey)
}

var survey = new Survey.Model(surveyJSON);
$("#surveyContainer").Survey({
    model: survey,
    onComplete: sendDataToServer
});

</script>
