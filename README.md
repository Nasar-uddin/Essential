<!DOCTYPE html>
<html>
<head>
	<title>Keywork checker</title>
</head>

<body>
	<div>
		<input type="text" id="text">
		<button id="check">Check</button>
	</div>
	<script type="text/javascript">
		var input = document.getElementById("text");
		document.getElementById("check").onclick = function(){
			if(isValidKeyWord(input.value))
				console.log("This is a valid keyword");
			else
				console.log("This is not a valid keyword");
		}
		/*
		var key = "_num";
		var keyworkPattren = /^([a-zA-Z_]+)([a-zA-Z\_\-0-9]*)$/;
		if(keyworkPattren.exec(key)){
			console.log("This is a valid keyword");
		}else{
			console.log("This is not a valid keywork");
		}
		*/
		function isValidKeyWord(words){
			var splitedKey = words.split(" ");
			if(splitedKey.length>2)
				return false;
			var isValidType = false;
			var dataType = ["int","long","byte","char","float","double"];
			var keyworkPattren = /^([a-zA-Z_]+)([a-zA-Z\_\-0-9]*)$/;
			dataType.forEach((type)=>{
				if(splitedKey[0]===type) isValidType=true;
			});

			if(!isValidType) 
				return false;
			else{
				if(keyworkPattren.exec(splitedKey[1])){
					return true;
				}else{
					return false;
				}
			}
		}
		
		
	</script>
</body>
</html>
