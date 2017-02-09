``` javascript
<script type="text/javascript">
			function slider(t,speed,delay){
				var t = t;
				var i = 0;
				var len = $(t+' .slider-box ul li').length;
				var box = $(t+' .slider-box');
				var ul = $(t+' .slider-box ul');
				var li = $(t+' .slider-box ul li');
				var slider_lock = true;
				$(t+' .btn .prev').on('click',function(){
					if(slider_lock){
						slider_lock = false;
						if(i > 0){i--;}
						move(i);
					}
				})
				$(t+' .btn .next').on('click',function(){
					if(slider_lock){
						slider_lock = false;
						if(i < len - 1){i++;}
						move(i);
					}
				})
				function move(n){
					ul.animate({'top':-n*li.eq(0).height()},speed,function(){
						slider_lock = true;
					});
				}
			}
			slider('.swiper-wrapper',500,5000);
		</script>
