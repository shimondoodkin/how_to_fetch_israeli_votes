# how_to_fetch_israeli_votes


install chrome extentnion:
https://chrome.google.com/webstore/detail/web-scraper-free-web-scra/jnhgnonknehpejjnehehllkliplmbmhn?hl=en




-----------


 the reseach on how to create was: 
 
 i used  
 https://www.knesset.gov.il/vote/heb/vote_search.asp

 and looked in inspector networking to see the post form values.
 
 then tried them as part of a get url, and it worked. because in Asp Classic programming language the prarameters used like request("param name") for post and for get.
 
 then in web scraper i added all links in the page using select and click of the application ui.
 
 then i parsed the next page elements using select and click of the application ui.
 
 i tried the application for one page and it worked, 
 
 i tried to click the next button but it did not work because of bug in scraper i guess because the urls stays the same
 
 so i tried a list of urls with params sent in post instead of clicking and it worked. 
 the urls param is start from number rounderd to 20
 
 when you use   https://www.knesset.gov.il/vote/heb/vote_search.asp you see 
 
רשימת הצבעות במליאה מתאריך: 1/1/2020 עד תאריך: 27/2/2021
1628 תוצאות נמצאו, מוצגים: 1 עד 20

the number of items is

1628

so rounded to 20 it is  1620

 
 i put few urls in scraping settings,  i exported the settings, found out there is alist of urls.
 
 i found out the urls are in reverse
 
i created  a list of url using excel

in vba escape char i duplicate the char, to escape quotes " i write it two times ""

in excel put in A1 
=",""https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=" & A2 & """"

put in A2 number of max items rounded up to 20
and fill it like:
(
drag down one step and put in B2 number-20

select both B1 and B2
drag down fill until all page numbers
double click on box edge of  url to fill the urls untill down
)

select column of urls and copy the urls paste them to the json
remove the first comma

import the updated scrapeing settings - the resulted json.
and try fetch.

i did it for from year 2020:
my json of scrapeing settings are:

-------------

to scrape again:


go to url:
https://www.knesset.gov.il/vote/heb/vote_search.asp

check "תאריך מ:"
and select from date

click search button חיפוש

see number of results:

רשימת הצבעות במליאה מתאריך: 1/1/2020 עד תאריך: 27/2/2021
1628 תוצאות נמצאו, מוצגים: 1 עד 20

the number of items is

1628


open dev tools inspector
right click and select inspect

shoose tab of web scaraper

import the following settings json:

```json

{"_id":"kneset2","startUrl":[
 "https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1620"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1600"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1580"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1560"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1540"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1520"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1500"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1480"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1460"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1440"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1420"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1400"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1380"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1360"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1340"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1320"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1300"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1280"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1260"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1240"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1220"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1200"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1180"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1160"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1140"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1120"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1100"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1080"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1060"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1040"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1020"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=1000"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=980"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=960"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=940"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=920"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=900"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=880"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=860"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=840"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=820"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=800"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=780"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=760"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=740"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=720"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=700"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=680"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=660"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=640"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=620"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=600"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=580"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=560"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=540"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=520"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=500"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=480"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=460"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=440"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=420"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=400"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=380"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=360"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=340"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=320"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=300"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=280"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=260"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=240"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=220"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=200"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=180"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=160"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=140"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=120"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=100"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=80"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=60"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=40"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=20"
,"https://www.knesset.gov.il/vote/heb/vote_res_list.asp?mk_individul_id_t=&ckMkIndiv=&RStart=0"


],"selectors":[{"id":"link","type":"SelectorLink","parentSelectors":["_root"],"selector":"a.DataText6","multiple":true,"delay":0},{"id":"sittingid","type":"SelectorText","parentSelectors":["link"],"selector":"center tr:contains('מספר ישיבה:') td.DataText6","multiple":false,"regex":"","delay":0},{"id":"voteid","type":"SelectorText","parentSelectors":["link"],"selector":"center tr:contains('מספר הצבעה:') td.DataText6","multiple":false,"regex":"","delay":0},{"id":"date","type":"SelectorText","parentSelectors":["link"],"selector":"center tr:contains('תאריך:') td.DataText6","multiple":false,"regex":"","delay":0},{"id":"name","type":"SelectorText","parentSelectors":["link"],"selector":"center tr:contains('שם החוק:') td.DataText6","multiple":false,"regex":"","delay":0},{"id":"headsit","type":"SelectorText","parentSelectors":["link"],"selector":"center tr:contains('יושב ראש:') td.DataText6","multiple":false,"regex":"","delay":0},{"id":"voteers","type":"SelectorHTML","parentSelectors":["link"],"selector":"[width='98%'] > tbody > tr","multiple":false,"regex":"","delay":0}]}



```

click scrape


then 


click on browse

after results are loaded




right click and select inspect on the results tables in the inspector

select from element browser the table of results:

   <table class="table table-bordered table-condensed table-hover">

run the following code:

$0 means the element selected

```javascript

data=[].slice.call($0.rows,0).map(r=>[].slice.call(r.cells,0).map(x=>x.innerText) )

div=document.createElement("DIV")


ss={
0:"בוטלו",
1:"בעד",
2:"נגד",
3:"נמנע",
4:"לא הצביע"
}




mm={
"ינואר"
:0
,
"פברואר"
:1
,
"מרץ"
:2
,
"אפריל"
:3
,
"מאי"
:4
,
"יוני"
:5
,
"יולי"
:6
,
"אוגוסט"
:7
,
"ספטמבר"
:8
,
"אוקטובר"
:9
,
"נובמבר"
:10
,
"דצמבר"
:11
}

data1=data.map(x=>{

x=x.slice(0);

// replace new lines in description to not cause problems later in excel
 x[7]=x[7].replace(/\n/g,"") 

// split the scraped html of votes in to tables, the tables are distinguished by background image see later

x[9]=x[9].split('<table width="100%" border="0" cellpadding="0" cellspacing="0" bgcolor="#F0EBE7">').slice(1).map(x=>'<table width="100%" border="0" cellpadding="0" cellspacing="0" bgcolor="#F0EBE7">'+x.split('</table>')[0]+'</table>').map(t=>{
 
 div.innerHTML=t; // parse html
 
 //take bakgroun image to identify what type of votes it is 
 var votefor=parseInt(div.querySelector("img").src.substr(-5).substr(0,1))

 //
 //[].slice.call( html_nodes_array_object ,start_from , take_amount (when omited then rest) ) converts to Array object that has the Array.map function so it can be used.
 
 var ta=[votefor,[].slice.call(div.firstElementChild.rows,0).map(r=>[].slice.call(r.cells,0).map(x=>x.innerText) )];

 var r=[];
 var t=ta[1];
 if(t[0][1]=="שם חבר כנסת")t=t.slice(1);
 if(t[t.length-1][1]=="")t=t.slice(0,t.length-1);
 prevsia="error"
 for(var name,sia, i=0;i<t.length;i++)
 {
  name=t[i][1];
  sia=t[i][2];
  if(sia.trim()=='"')
   sia=prevsia;
  prevsia=sia;
  r.push([name,sia])
 }
 return [ta[0],r];

 })
try{
var d=x[6].replace(/[^0-9א-ת]+/g, " ").split(/ /).map(x=>x).slice(3);d[1]=""+mm[d[1]];d=d.map(x=>parseInt(x)); var dd=new Date(d[2],d[1],d[0],d[3],d[4]) ;
var date=dd.toISOString().substr(0,10);
var time=dd.toTimeString().substr(0,5);
var utime=dd.getTime();
var s=[dd,date,time,utime,parseInt(x[3].split('=')[1]),x[3],x[6],x[7]];
}
catch(e){ 

var s=[null,"","",0,x[3],x[6],x[7]];

console.log('date parse error ',x); }
 

x[10]=[].concat(...x[9].map(t=>t[1].map(r=>s.concat([r[0],r[1],t[0],ss[t[0]]]))));

 return x;
});

data2=[].concat(...data1.map(x=>x[10]));

```



now it is time to save data1 and data2



for excel:

["date	day	time	unixtime	voteid	voteurl	datetext	law	user	group	votefor	votefortext".split(/\s+/),...data2].map(row=>row.join('\t')).filter(r=>r.length>0).join('\n')


click copy , paste it into excel as is, excel accpets data that is seperated by tabs and new lines as a table

now in excel use pivot table to work with data


// to save it as regulare json

JSON.stringify(data1)
click copy paste in a text file and save

JSON.stringify(data2)
click copy paste in a text file and save



// for turnilo

data1str=data1.map(x=>JSON.stringify(x)).join('\n')
click copy paste in a text file and save
data2str=data1.map(x=>JSON.stringify(x)).join('\n')
click copy paste in a text file and save






