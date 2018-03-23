JavaScript檢查欄位方法

取得輸入欄位值
	EX: <input type="text" id="usernameid" name="username" class="">

	1. javascript方式
		var val = document.getElementById("usernameid").value

	2. JQuery方式
		用id取值
		var val = $('#usernameid').val()
		用name取值
		var val = $('input[name=username]').val()

檢查欄位值長度
	1. 取得值長度
		val.length
	2. 檢查值
		var val = document.getElementById("usernameid").value;
		var size = val.length;
		if ((size < 6) || (size > 12))
			alert('字串長度不在6~12');

檢查欄位值字元
	1. 最簡單方式
		//charAt(index) => 用來取得字串的第index個字元, index從0開始
		EX: 檢查輸入值只能是0,1,2
		var val = document.getElementById("usernameid").value;
		var size = val.length;
		var vaildChar = ['0','1','2']; //設定合法字元的陣列，取得值的方式vaildChar[index]
		for (i=0;i<size;i++) { //用來取得val每個字元的迴圈

			var failed = 1; //設變數, 先假設取得的這個字元不在合法的字元內(vaildChar)
			for(j=0;j<vaildChar.length;j++) { //用來取得vaildChar每個字元的迴圈
				if (val.charAt(i) == vaildChar[j]) { //檢查字元，與vaildChar的字元是不是一樣
					failed = 0; //字元一樣，把變數設定這個字元是合法的
					break; //跳出迴圈
				}
			}

			if (failed == 1) { //字元跟vaildChar的每個字元比對後，還是不合法，做提示訊息
				alert("輸入字元錯誤");
				break; //跳出迴圈
			}
		}

