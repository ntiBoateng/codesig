# codesig


`````

var object = {0: "Zero" ,1 : "One", 2: "Two", 3 : "Three", 4 :"Four", 5: "Five",  6 :"Six", 7: "Seven", 8: "Eight", 9: "Nine"}

var tenToTwenty = {10: "Ten", 11: "Eleven", 12:"Twelve",13: "Thirteen", 14: "Fourteen", 15: "Fifteen", 16: "Sixteen", 17: "Seventeen",  18: "Eighteen", 19 : "Nineteen"}

var twentyToHundred = {2: "Twenty",3: "Thirty", 4: "Forty",  5: "Fifty",6: "Sixty",7 : "Seventy", 8: "Eighty", 9: "Ninety"}

var bigger = {2 : "Hundred", 4: "Thousand",  6: "Million",9: "Billion"}
 var returnList = [];

function solution(num) {
if(num < 10){
    return object[num]
}

if(num >=10){
   while(num >=10){
       num -= convertBigger(num)
}}

if(num < 10 && num > 0){
    returnList.push(object[num])
}
returnList = returnList.join("")
if(returnList.charAt(returnList.length-1) === " "){
   returnList  = returnList.substring(0,returnList.length-1)
}
return returnList
}

function convertBigger(n){
 var toReturn =  n < 1000 ? caseBelowThousand(n): n>=1000&&n<1000000?caseThousands(n): n>=1000000&&n<1000000000?caseMillions(n):caseBillions(n);
 console.log(toReturn)
 return toReturn;
}
function caseBelowThousand(n){
    if(n < 20) {
        returnList.push(tenToTwenty[n]);
        return n;
    }
     if(n >=20 && n <100){
         returnList.push(twentyToHundred[Math.floor(n/10)]+" ")
        return Math.floor(n/10)*10;
    }
    if(n >=100 && n < 1000){
        returnList.push(object[Math.floor(n/100)] + " Hundred ")
        return Math.floor(n/100)*100
    }
}

 function caseThousands(n){
     if(n >=1000 && n < 10000){
        returnList.push(object[Math.floor(n/1000)] + " Thousand ")
        return Math.floor(n/1000)*1000
    }
     if(n >=10000 && n < 20000){
        returnList.push(tenToTwenty[Math.floor(n/1000)] +" Thousand ")
         return Math.floor(n/1000)*1000
    }
    if(n >=20000 && n < 100000){
        var test = n-(Math.floor(n/10000)*10000)
        test = Math.floor(test/1000)
        if(test === 0){
            returnList.push(twentyToHundred[Math.floor(n/10000)] + " Thousand ")
        }
        else{
        returnList.push(twentyToHundred[Math.floor(n/10000)] + " "+ object[test] + " Thousand ")
        }
         return Math.floor(n/1000)*1000
    }
    if(n >=100000 && n < 1000000){
        var test = n-(Math.floor(n/100000)*100000)
        if(test < 1000){
            returnList.push(object[Math.floor(n/100000)] + " Hundred Thousand ")
        }
        else{
        returnList.push(object[Math.floor(n/100000)] + " Hundred ")

        }
         return Math.floor(n/100000)*100000
    }

 }
function caseMillions(n){
    if(n >=1000000 && n < 10000000){
        
        returnList.push(object[Math.floor(n/1000000)] + " Million ")
         return Math.floor(n/1000000)*1000000
    }
    if(n >=10000000 && n < 20000000){
        
        returnList.push(tenToTwenty[Math.floor(n/1000000)] + " Million ")
         return Math.floor(n/1000000)*1000000
    }
    if(n >=20000000 && n < 100000000){
        var test = n-(Math.floor(n/10000000)*10000000)
        test = Math.floor(test/1000000)
        if(test === 0){
            returnList.push(twentyToHundred[Math.floor(n/10000000)] +" Million ") 
        }
        else{
returnList.push(twentyToHundred[Math.floor(n/10000000)] + " "+ object[test] +" Million ")        }
        
         return Math.floor(n/1000000)*1000000
    }
     if(n >=100000000 && n < 1000000000){
         var test = n-(Math.floor(n/100000000)*100000000)
        if(test < 1000000){
            returnList.push(object[Math.floor(n/100000000)] + " Hundred Million ")
        }
else{
        returnList.push(object[Math.floor(n/100000000)] + " Hundred ")
}
        return Math.floor(n/100000000)*100000000
    }

}


function caseBillions(n){
   returnList.push(object[Math.floor(n/1000000000)] + " Billion ")
    return Math.floor(n/1000000000)*1000000000
    
}


```
