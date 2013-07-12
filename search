var day1=parseInt('0');var day2=parseInt('1');function MM_openBrWindow(theURL,winName,features,formname){var url=theURL;url+="?firstName=";url+=document.forms[formname].firstName.value;url+="&lastName=";url+=document.forms[formname].lastName.value;url+="&uniqueId=";url+=document.forms[formname].sui.value;url+="&memberId=";url+=document.forms[formname].memberID.value;url+="&pageId=";url+=document.forms[formname].pageId.value;window.open(url,winName,features);}
function initializeDate(){var f=document.resortFlow2a.elements;arrDate=new Date();depDate=new Date();var today=new Date();arrDate.setDate(arrDate.getDate()+day1);depDate.setDate(depDate.getDate()+day2);f["arrive_month"].value=arrDate.getMonth()+1;f["depart_month"].value=depDate.getMonth()+1;addDynamicDropDown('1');addDynamicDropDown('2');f["arrive_day"].value=arrDate.getDate();if(arrDate.getFullYear()){f["arrive_year"].value=arrDate.getFullYear();}
if(f["arrive_year"].value=='')
f["arrive_year"].value=today.getFullYear();f["depart_day"].value=depDate.getDate();if(depDate.getFullYear()){f["depart_year"].value=depDate.getFullYear();}
if(f["depart_year"].value=='')
f["depart_year"].value=today.getFullYear();f["defaultDay1"].value=arrDate.getDate();f["defaultDay2"].value=depDate.getDate();f["defaultMonth1"].value=arrDate.getMonth()+1;f["defaultMonth2"].value=depDate.getMonth()+1;f["defaultYear1"].value=arrDate.getFullYear();f["defaultYear2"].value=depDate.getFullYear();}
function initializeDateAgain(arriveMonth,departMonth,arriveDay,departDay,arriveYear,departYear){var f=document.resortFlow2a.elements;var today=new Date();addDynamicDropDown('1');addDynamicDropDown('2');f["arrive_month"].value=arriveMonth;f["depart_month"].value=departMonth;f["arrive_day"].value=arriveDay;f["depart_day"].value=departDay;f["arrive_year"].value=arriveYear;f["depart_year"].value=departYear;f["defaultDay1"].value=arrDate.getDate();f["defaultDay2"].value=depDate.getDate();f["defaultMonth1"].value=arrDate.getMonth()+1;f["defaultMonth2"].value=depDate.getMonth()+1;f["defaultYear1"].value=arrDate.getFullYear();f["defaultYear2"].value=depDate.getFullYear();}
function changeDepartYear(){arriveYear=document.forms['resortFlow2a'].arrive_year.value;document.forms['resortFlow2a'].depart_year.value=arriveYear;addDynamicDropDown('3');addDynamicDropDown('1');}
function changeURL(rId){document.resortFlow2a.action='obe_step2.do';document.resortFlow2a.resortId.value=rId;document.resortFlow2a.firstDisplay.value='true';document.resortFlow2a.submit();}
function calculateBalance(vacCost){var cost=parseInt(vacCost);var sum=0;for(var i=0;i<document.mempoints.contractpoints.length;i++){var val=document.mempoints[document.mempoints.contractpoints[i].value].value;if(val==''){val='0';}
sum=sum+parseInt(val);}
if(document.mempoints.contractpoints.length==undefined){var val=document.mempoints[document.mempoints.contractpoints.value].value;if(val==''){val='0';}
sum=sum+parseInt(val);}
document.mempoints.pointbalance.value=sum-cost;}
function checkPointValue(vacCost){if(calculateBalance(vacCost)!=false){var cost=parseInt(vacCost);if(parseInt(document.mempoints.pointbalance.value)==0){document.mempoints.submit();return true;}
if(parseInt(document.mempoints.pointbalance.value)>0){alert('Too many points were given to pay off the balance');}else{alert('More points are needed to pay off the balance');}
return false;}}
function populateDropDowns(f,value){for(var i=0;i<f.length;i++){if(f.options[i].value==value){f.options[i].selected=true;}}}
function checkFirst(field)
{i=0;if(field.length==null)
field.checked=true;else
field[i].checked=true;}
function isLeapYear(y){if(y%4==0){if(y%100==0)return(y%400==0)?true:false;return true;}
return false;}
function validateDate(){var f=document.resortFlow2a.elements;var month=new Array('January','February','March','April','May','June','July','August','September','October','November','December');var arrive_year=parseInt(f["arrive_year"].value);var depart_year=parseInt(f["depart_year"].value);var arrive_month=parseInt(f["arrive_month"].value);var depart_month=parseInt(f["depart_month"].value);var arrive_day=parseInt(f["arrive_day"].value);var depart_day=parseInt(f["depart_day"].value);var defaultYear1=parseInt(f["defaultYear1"].value);var defaultYear2=parseInt(f["defaultYear2"].value);var defaultMonth1=parseInt(f["defaultMonth1"].value);var defaultMonth2=parseInt(f["defaultMonth2"].value);var defaultDay1=parseInt(f["defaultDay1"].value);var defaultDay2=parseInt(f["defaultDay2"].value);var today=new Date();var depart=new Date();var arrival=new Date();var default1=new Date();var default2=new Date();var memberType=document.forms['resortFlow2a'].elements['memberType'].value;default1.setFullYear(defaultYear1,defaultMonth1-1,defaultDay1);default2.setFullYear(defaultYear2,defaultMonth2-1,defaultDay2);depart.setFullYear(depart_year,depart_month-1,depart_day);arrival.setFullYear(arrive_year,arrive_month-1,arrive_day);var oneDay=24*60*60*1000;var firstDate=new Date(arrive_year,arrive_month-1,arrive_day);var secondDate=new Date(today.getFullYear(),today.getMonth(),today.getDate());var diffDays=Math.abs((firstDate.getTime()-secondDate.getTime())/(oneDay));if(arrival>depart)
{alert('Arrival date should come before departure date.');initializeDate();return false;}
else if(arrival<default1)
{if(day1==0)
alert('OBE Engine requires arrival dates to be on or after today.\n\nPlease set the arrival date to on or after '+month[default1.getMonth()]+' '+default1.getDate()+' '+default1.getFullYear()+'.');else
alert('OBE Engine requires arrival dates to be at least '+day1+' days from today.\n\nPlease set the arrival date to on or after '+month[default1.getMonth()]+' '+default1.getDate()+' '+default1.getFullYear()+'.');initializeDate();return false;}
else if((arrive_month==depart_month)&&(arrive_day>=depart_day)){alert('Please enter a valid departure day. \nDeparture day should be at least one day after arrival day.');initializeDate();return false;}
else if((memberType=='navigator'||memberType=='explorer')&&diffDays<14){alert('Arrival date must be 14 days or greater from today.');initializeDate();return false;}
return true;}
function popUpExplorer(){var memberType=document.forms['resortFlow2a'].elements['memberType'].value;if(memberType=='explorer'||memberType=='navigator'){var confirmBox=confirm('Your loan must be paid in full 14 days prior to arrival or your reservation will be cancelled and points forfeited.');if(confirmBox)
document.forms['resortFlow2a'].submit();else
alert('Hi');}
else{document.forms['resortFlow2a'].submit();}}
function addDynamicDropDown(choice){var f=document.resortFlow2a.elements;if(choice=='3'){switch(f["arrive_month"].value){case"2":document.forms['resortFlow2a'].arrive_day.options.length=0;if(isLeapYear(f["arrive_year"].value)){for(var x=1;x<=29;x++)
document.forms['resortFlow2a'].arrive_day.options[x-1]=new Option(x,x);}
else{for(var x=1;x<=28;x++)
document.forms['resortFlow2a'].arrive_day.options[x-1]=new Option(x,x);}
break;}}
else if(choice=='4'){switch(f["depart_month"].value){case"2":document.forms['resortFlow2a'].depart_day.options.length=0;if(isLeapYear(f["depart_year"].value)){for(var x=1;x<=29;x++)
document.forms['resortFlow2a'].depart_day.options[x-1]=new Option(x,x);}
else{for(var x=1;x<=28;x++)
document.forms['resortFlow2a'].depart_day.options[x-1]=new Option(x,x);}
break;}}
if(choice=='1'){document.forms['resortFlow2a'].arrive_day.options.length=0;switch(f["arrive_month"].value){case"1":case"3":case"5":case"7":case"8":case"10":case"12":for(var x=1;x<=31;x++)
document.forms['resortFlow2a'].arrive_day.options[x-1]=new Option(x,x);break;case"4":case"6":case"9":case"11":for(var x=1;x<=30;x++)
document.forms['resortFlow2a'].arrive_day.options[x-1]=new Option(x,x);break;case"2":if(isLeapYear(f["arrive_year"].value))
for(var x=1;x<=29;x++)
document.forms['resortFlow2a'].arrive_day.options[x-1]=new Option(x,x);else
for(var x=1;x<=28;x++)
document.forms['resortFlow2a'].arrive_day.options[x-1]=new Option(x,x);break;}}
else{document.forms['resortFlow2a'].depart_day.options.length=0;switch(f["depart_month"].value){case"1":case"3":case"5":case"7":case"8":case"10":case"12":for(var x=1;x<=31;x++)
document.forms['resortFlow2a'].depart_day.options[x-1]=new Option(x,x);break;case"4":case"6":case"9":case"11":for(var x=1;x<=30;x++)
document.forms['resortFlow2a'].depart_day.options[x-1]=new Option(x,x);break;case"2":if(isLeapYear(f["depart_year"].value))
for(var x=1;x<=29;x++)
document.forms['resortFlow2a'].depart_day.options[x-1]=new Option(x,x);else
for(var x=1;x<=28;x++)
document.forms['resortFlow2a'].depart_day.options[x-1]=new Option(x,x);break;}}}
function setDepature(dateF)
{var f=document.resortFlow2a.elements;var arrive_year=parseInt(f["arrive_year"].value);var depart_year=parseInt(f["depart_year"].value);var arrive_month=parseInt(f["arrive_month"].value);var depart_month=parseInt(f["depart_month"].value);var arrive_day=parseInt(f["arrive_day"].value);var depart_day=parseInt(f["depart_day"].value);var depart=new Date();var arrival=new Date();depart.setFullYear(depart_year,depart_month-1,depart_day);arrival.setFullYear(arrive_year,arrive_month-1,arrive_day);var dayDiff=Math.ceil(((depart.getTime()-arrival.getTime())/(1000*60*60*24)));if(!f["firstDisplay"]){switch(dateF)
{case"y":document.forms['resortFlow2a'].depart_year.value=arrive_year;break;case"m":document.forms['resortFlow2a'].depart_year.value=arrive_year;case"d":break;}}}
function toggleLayer(whichLayer,visibility){var elem;var vis;if(document.getElementById)
elem=document.getElementById(whichLayer);else if(document.all)
elem=document.all[whichLayer];else if(document.layers)
elem=document.layers[whichLayer];if(elem!=null){vis=elem.style;if(visibility=='display'){vis.display='block';}
if(visibility=='hide'){vis.display='none';}}}
function notAllowed()
{alert('Sorry, but this feature has been disabled for this user');return false;}
function changeDepartMonth(){arriveMonth=document.forms['resortFlow2a'].arrive_month.value;document.forms['resortFlow2a'].depart_month.value=arriveMonth;addDynamicDropDown('2');}
function numberOnly(e)
{var keynum
var keychar
var numcheck
if(window.event)
{if((e.keyCode>=48&&e.keyCode<58)||(e.keyCode==8)||(e.charCode==0))
{return true}
else{return false}}
else if(e.which)
{if((e.charCode>=48&&e.charCode<58)||(e.charCode==8)||(e.charCode==0)){return true}else{return false}}}
