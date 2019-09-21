```js

var myFunc = function(a, b){
    var x = a + b;
    return x;
}

function myFunc2(a,b){
    var x = a*b;
    return x;
}

var myFunc3 = (a,b)=>{
    var x = a*b+15;
    return x;
}

var array = [
    {a:1},
    {a:2},
    {a:3},
    {a:4}
];

console.log( array.filter(x=>x.a>2) )
console.log( array.filter(function(x){
    return x.a > 2
}));
console.log( array.filter((x)=>{
    return x.a > 2
}));

console.log('result:', myFunc(4, 10) )
console.log('result2:', myFunc2(4, 10) )
console.log('result3:', myFunc3(4, 10) )

//////////

function howMuchGays(human_amount){
    return (human_amount*0.25)+" gays"
}

function howMuchBlack(human_amount){
    return (human_amount*0.4)+" black people"
}

function howMuchWomen(human_amount){
    return (human_amount*0.5)+" women"
}

function analysPeople(amount){
    var gays = howMuchGays(amount);
    var black = howMuchBlack(amount);
    var women = howMuchWomen(amount);
    return [gays, black, women];
}

console.log( analysPeople(2133) )



//////////

/**

    count( [1,2,3,4] );

    -> 10

*/


 function count( arr ){
     var sum = 0;
    //  arr.map(num=>sum+=num);
    for(var num of arr) sum += num
    return sum;
 }

 var sum = count([1,2,3,4,5,6]);

 console.log( sum )


 ///////////


/**

square(4, 5);
-> 20 кв. м.

square(48, 50);
-> *** кв. м. - очень большая хата

*/

function square(a, b){
    var res = {sq: a*b, text:' кв.м.'};
    if (res.sq>400) res.text += ' - очень большая хата!!!1'
    return res.sq + res.text 
}
console.log(square(5,100))

//////////


/**

smartEncoder( [1090, 1099, 32, 1087, 1080, 1076, 1086, 1088] );
-> "ты пидор"

smartEncoder( "ты пидор" );
-> [1090, 1099, 32, 1087, 1080, 1076, 1086, 1088]

*/

/**

var array = [1090, 1099];
String.fromCharCode(...array)
-> "ты"

"ты".charCodeAt(0);
-> 1090

*/






function stringCharCodes(a){
    var res1 = [];
    for (var i in a){ 
        res1.push(a.charCodeAt(i));
    }
    return res1
};

function smartEncoder(a){
   if (typeof a == "string") return stringCharCodes(a)
   if (typeof a == "object") return String.fromCharCode(...a)
};

console.log(smartEncoder([ 1090, 1099, 32, 1087, 1080, 1076, 1086, 1088 ]))

```
