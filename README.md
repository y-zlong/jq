# jq
基于jq开发轮播图


仿京东首页轮播图，实现淡入淡出切换效果。
$(function(){
		$(".img li").eq(0).show();  //初始化显示第一张图片   
		
	$(".num li").mouseover(function(){                                                  //鼠标移入事件
		$(this).addClass("active").siblings().removeClass("active");
		i=index;	                                                                       //索引值的对应
	$(".img li").eq(index).stop().fadeIn().siblings().stop().fadeOut();   
	})
	
	var i=0;
	var timer=setInterval(move,3000) 
	function move(){                
	 i++;
	 if(i==5){
	 	i=0
	 	}
		$(".num li").eq(i).addClass("active").siblings().removeClass("active");
		$(".img li").eq(i).fadeIn().siblings().fadeOut();
	}
	function move1(){            
	 if(i==-1){
	 	i=5
	 	}
		$(".num li").eq(i).addClass("active").siblings().removeClass("active");
		$(".img li").eq(i).fadeIn().siblings().fadeOut();
	}
	$(".warp").hover(function(){           
				clearInterval(timer)
			},function(){                 
				timer=setInterval(move,3000)
				})


	$(".left").click(function(){			
		move1()
	})
	$(".right").click(function(){			
		move()
	})



})

