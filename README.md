jquery-json-cookie
==================

用cookie存储json数据。依赖于：jquery.js；jquery.cookie.js；json2.js；

## 用法

		var obj;
		jQuery(function ($) {
			$('#store').click(function () {
				var name = $('#cookieName').val(),
					val = $('#cookieObject').val();
				eval('obj = ' + val, window);
				$.JSONCookie(name, obj, {path: '/'});
				return false;
			});
			
			$('#retrieve').click(function () {
				var name = $('#cookieName').val(),
					o = $.JSONCookie(name);
				$('#cookieObject').val('').val(JSON.stringify(obj));
				return false;
			});
			
			$('#log').click(function () {
				var name = $('#cookieName').val(),
					o = $.JSONCookie(name);
				if (window.console && console.log) {
					console.log(o);
				}
				return false;
			});
		});
