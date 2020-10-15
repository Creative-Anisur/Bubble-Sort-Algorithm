<html>
    <head>
      
     <style>
      body {
    
}
#myCanvas{
    border:solid 1px;
    width:100%;
    
   
    
}
#wrapper{
    background:pink;
    overflow:auto;
    font-family:"Times New Roman";
   
}
#slow{
   float:left;
}
#fast{
    float:right;
}
#algorithmDetails{
    font-family:"Times New Roman";
    border:solid 1px;
}
#animSpeed{
   width:100%; 
}
      
</style>
        <title>Bubble Sort Demo</title> 
    </head>
    <body>
    <center><canvas id="myCanvas"></canvas></center>
        <br />
        <input id="animSpeed" value="-33" type="range" min="-33" max="-1">
        <br />
        <div id="wrapper">
        <span id="slow">slow</span>
        <span id="fast">fast</span>
        </div>
        <div id="controlPanel">
            <button id="shuffleArray">Shuffle Array</button>
            <button id="bubbleSort">Bubble Sort</button>
            <select id="selectOrder">
                <option value="ascending">Ascending Order</option>
                <option value="descending">Descending Order</option>
            </select>
            <br />
            <div id="info"></div>
            <br />
            <div id="debug"></div>
            <br><br>
            <p id="algorithmDetails"><b><a href="https://bn.wikipedia.org/wiki/%E0%A6%AC%E0%A6%BE%E0%A6%AC%E0%A6%B2_%E0%A6%B8%E0%A6%B0%E0%A7%8D%E0%A6%9F">বাবল সর্ট: উইকিপিডিয়া, মুক্ত বিশ্বকোষ থেকে:</a></b><br><br>
 বাবল সর্ট (ইংরেজিঃ Bubble sort) সর্টিং অ্যালগোরিদমগুলোর মধ্যে সবচেয়ে সহজ এবং ছোট অ্যালগোরিদম।
এই অ্যালগোরিদমে যে প্রক্রিয়াটি অনুসরণ করা হয় তা হল প্রথমে একটি অ্যারের উপাদান নির্দিষ্ট করে ধরে নেওয়া হয়। তারপর সেই অ্যারের উপাদানের সাথে অন্যান্য উপাদানগুলোকে তুলনা করা হয়। যদি পাশাপাশি উপাদান দুটির মধ্যে আগের উপাদানটি যদি পরেরটির চেয়ে বড় হয় (ছোট থেকে বড় ক্রমে সাজানোর জন্য) অথবা ছোট হয় (বড় থেকে ছোট ক্রমে সাজানোর জন্য) তাহলে উপাদান দুটির পারস্পরিক স্থান পরিবর্তন (swap) করা হয়। এভাবে সবগুলো উপাদান একবার করে নিয়ে যতক্ষণ পর্যন্ত উপাদানগুলোর পারস্পরিক স্থান পরিবর্তন হবে ততক্ষণ পর্যন্ত একই কাজের পুনরাবৃত্তি করা হয়।পারস্পরিক স্থান পরিবর্তন না হওয়ার মানে হল অ্যারেটির সর্টিং হয়ে গেছে। <br> <br> মনে করি, একটি অ্যারের উপাদানগুলো যথাক্রমে "5 1 4 2 8", এবং এই উপাদানগুলোকে ছোট থেকে বড় ক্রমে সাজাতে হবে । প্রতি ধাপে, গাঢ় উপাদান গুলোর মধ্যে তুলনা করা হবে । এর জন্য তিনটি ধাপ প্রয়োজন । <br><br>

<b>প্রথম ধাপ:</b><br>
( 5 1 4 2 8 )→( 1 5 4 2 8 ), এখানে, প্রথম দুটি উপাদানের মধ্যে তুলনা করবে, এবং যেহেতু 5 > 1 সেহেতু স্থান পরিবর্তন করবে।<br>
( 1 5 4 2 8 )→( 1 4 5 2 8 ), যেহেতু 5 > 4 সেহেতু স্থান পরিবর্তন করবে.।<br>
( 1 4 5 2 8 )→( 1 4 2 5 8 ), যেহেতু 5 > 2 সেহেতু স্থান পরিবর্তন করবে।<br>
( 1 4 2 5 8 )→( 1 4 2 5 8 ), এখন, যেহেতু (8 > 5), সেহেতু স্থান পরিবর্তন করবে না।<br><br>

<b>দ্বিতীয় ধাপ:</b> <br>
( 1 4 2 5 8 )→( 1 4 2 5 8 ) <br>
( 1 4 2 5 8 )→( 1 2 4 5 8 ), যেহেতু 4 > 2 সেহেতু স্থান পরিবর্তন করবে।<br>
( 1 2 4 5 8 )→( 1 2 4 5 8 )<br>
এখন, এই উপাদানগুলো ক্রমানুসারে আছে,কিন্তু অ্যালগোরিদমটি অ্যারের উপাদানগুলো সর্ট হয়েছে বা ক্রমানুসারে আছে কি না সেটা নিশ্চিত নয়। <br>
উপাদানগুলো ক্রমানুসারে আছে সেটা নির্ধারণ করার জন্য উপাদানগুলোর স্থান পরিবর্তন না করে পুনরায় একটি পূর্ণাঙ্গ ধাপের দরকার হয় ।<br><br>

<b>তৃতীয় ধাপ:</b><br>
( 1 2 4 5 8 )→( 1 2 4 5 8 )<br>
( 1 2 4 5 8 )→( 1 2 4 5 8 )<br><br>
<b>চতুর্থ ধাপ:</b><br>
( 1 2 4 5 8 )→( 1 2 4 5 8 )<br><br>
            Complexity:<br>
            Worst-case: O(n<sup>2</sup>)<br>
            Best-case: O(n)<br>
            Average Performance: O(n<sup>2</sup>)<br><br>
            <pre>
Implementation:
input: a as an array to be sorted
output: sorted array a

function bubbleSort(a){
    var swapped;
    do{
        swapped = false;
        for(var i=0; i < a.length-1; i++){
            if(a[i] > a[i+1]){
                var temp = a[i];
                a[i] = a[i+1];
                a[i+1] = temp;
                swapped = true;
            }
        }
    }while(swapped);
}
            </pre>
            
            </p>
        </div>
    </body>
</html>

<script>


function shuffle (array) {
  var i=0,j=0,temp=null;
  for (i = array.length - 1; i > 0; i -= 1) {
    j = Math.floor(Math.random() * (i + 1))
    temp = array[i];
    array[i] = array[j];
    array[j] = temp;
    
    temp=array[i].x;
    array[i].x=array[j].x;
    array[j].x=temp;
  }
  return array;
}


function randVal(min, max) {
    return (Math.floor(Math.random()*(max - min + 1) + min));
}
function randFloat(min, max) {
    return (Math.random()*(max - min + 1) + min);
}


function start(){
    myCanvas=document.getElementById("myCanvas");
    ctx=myCanvas.getContext("2d");
    var widthRatio=0.9;
    var heightRatio=0.50;

    myCanvas.width = window.innerWidth*widthRatio;
    myCanvas.height = window.innerHeight*heightRatio;
    
    var barSettings={
        width:20,
        heightMultiplier:20,
        margin:12,
        
    }
    var delay={
       checkSortDelay:1000,
       swapAnimationDelay:33,
       swapTimeoutDelay:1500
    }
     document.getElementById("animSpeed").onchange=function(){
       delay.swapAnimationDelay=Math.abs(document.getElementById("animSpeed").value); delay.swapTimeoutDelay=(barSettings.width+barSettings.margin)*delay.swapAnimationDelay+700;
        //alert(delay.swapTimeoutDelay);
    }
     
    var swapInterval=null;
    var swappingFlag=false;
    var colorsArray=["yellow","black","red","green","blue","orange","purple","lightgreen","pink"]
    var barsArray=[];
    
    document.getElementById("shuffleArray").onclick=function(){
        barsArray=shuffle(barsArray);
        drawBars();
    }
   
 function descending(a,b){return b<a;}
 function ascending(a,b){return b>a;}
  document.getElementById("bubbleSort").onclick=function(){
        document.getElementById("shuffleArray").disabled=true;
        document.getElementById("bubbleSort").disabled=true;
       document.getElementById("selectOrder").disabled=true;
        func=document.getElementById("selectOrder").value;
        bubbleSort(barsArray,eval(func));
        
        sortInterval=setInterval(function(){
            sorted=true;
            for(i=0;i<barsArray.length-1;i++){
               if(barsArray[i].x>barsArray[i+1].x){
                   sorted=false;
               }
            }
            if(sorted){
               clearInterval(sortInterval);
               document.getElementById("shuffleArray").disabled=false; document.getElementById("bubbleSort").disabled=false; document.getElementById("selectOrder").disabled=false; document.getElementById("info").innerHTML="All Done!";
            }
        },delay.checkSortDelay);
        
    }
    
    xBuffer=barSettings.margin*2;
    for(i=1;i<10;i++){
        barsArray.push({
            value:i,
            width:barSettings.width,
            height:barSettings.heightMultiplier*i,
            x:xBuffer,
            y:myCanvas.height-barSettings.heightMultiplier*i-10,
            color:colorsArray[i%colorsArray.length]
        });
        xBuffer+=barSettings.width+barSettings.margin;
    }
    
    function drawBars(){
        ctx.fillStyle="lightblue"; ctx.fillRect(0,0,myCanvas.width,myCanvas.height);
        xBuffer=barSettings.margin*2;
        for(i=0;i<barsArray.length;i++){
            bar=barsArray[i];
            ctx.beginPath();
            ctx.fillStyle=bar.color;
            ctx.rect(bar.x,bar.y,bar.width,bar.height);
            
            ctx.fill(); 
            ctx.font="20px Times New Roman";
            ctx.fillStyle="black"; ctx.fillText(bar.value,bar.x+barSettings.width/4,bar.y-barSettings.margin);
            ctx.closePath();
            
        }
    }
    
    function swapBars(barA,barB,compFunc){

        function swapAnimation(){
                 
            if((barA.x>=xB || barB.x<=xA) || (xFakeA>=xB || xFakeB<=xA)){
                clearInterval(swapInterval);
                swapInterval=null;
                swappingFlag=false;
                barA.color=cA;
                barB.color=cB;
            }
            else{
                if(compFunc(barA.value,barB.value)){
                    barA.x++;
                    barB.x--;
                }
                xFakeA++;
                xFakeB--;
            }
            drawBars();
        }
        
        if(!swapInterval){
            xA=barA.x;
            xB=barB.x;
            xFakeA=barA.x;
            xFakeB=barB.x;
            cA=barA.color;
            cB=barB.color;
            swapColor=(compFunc(barA.value,barB.value)? "white":"gray");
            barA.color=swapColor;
            barB.color=swapColor;
            swappingFlag=true;
           document.getElementById("info").innerHTML=barA.value + ((document.getElementById("selectOrder").value=="ascending")? " > ":" < ") + barB.value + ((compFunc(barA.value,barB.value))? " --> SWAP!":" --> NO SWAP!");
            swapInterval=setInterval(swapAnimation ,delay.swapAnimationDelay);
        }
        else{
            setTimeout(swapBars.bind(null,barA,barB,compFunc),delay.swapTimeoutDelay);
        }
        //swapInterval=setInterval(swapAnimation.bind(null,barsArray[0],barsArray[1]),33);
    }
    
    function bubbleSort(a,compFunc){
        var swapped;
        //do
         for(j=0;j<a.length-1;j++){
            swapped = false;
            for (var i=0; i < a.length-1-j; i++) {
            // run one less iteration each round as the right side is already sorted
            
            //document.getElementById("debug").innerHTML+=a[i].value+" > "+a[i+1].value+" "+((a[i].value > a[i+1].value)? "V":"X")+";\n";
                //if (a[i].value > a[i+1].value) 
                swapBars(a[i],a[i+1],compFunc);
                if(compFunc(a[i].value,a[i+1].value))
                {
                    var temp = a[i];
                    a[i] = a[i+1];
                    a[i+1] = temp;
                    
                    swapped = true;
                }
            }
            if(!swapped){
            // no swaps were made in the inner loop --> all sorted
               break; 
            }
        }// while (swapped);
    }
    drawBars();
}

window.onload=start;





</script>
