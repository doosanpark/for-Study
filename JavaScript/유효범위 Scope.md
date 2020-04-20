# 유효범위 Scope



```javascript
var scope="global";

function fscope(){

	var vscope = 'local';
	var lv = 'local variables';
	alert(lv);

}

fscope();
alert(lv);	//undefined
```



```javascript
var vscope ='global';
function fscope(){
	var vscope = 'local';
	fscope();
	alert(vscope);
}

//결과는 global
```



scope는 로직의 충돌을 회피하기 위해 고안됨

```javascript
function a(){
	i = 0;
}
for(var i = 0; i < 5; i++){
	a();
	document.write(i);
}

//결과는 무한루프
```



함수가 선언된 시점에서의 유효범위를 갖는다.

```javascript
var i = 5;

function a(){
	var i = 10;
	b();
}

function b(){
	document.write(i);
}
a();

//여기에서 i는 누구?
//현재 지역변수는 없으니 전역변수를 찾는다.
//답은 5
```

