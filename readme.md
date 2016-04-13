1.html
	转盘抽奖
	使用方法：
	1.引入jquery、awardRotate.js
	2.引入style.css
	3.在页面中加入demo中的js
	说明：
	turnplate.restaraunts 数组可以用来存放奖品的名字，最后停下来后默认给用户展示的就是这里存放的名字
	turnplate.colors 数组用来存放单个奖品的背景颜色，需要和turnplate.restaraunts一一对应
	rnd()函数可以随机指定最后转盘停下来的位置，实际开发中这个函数的返回结果可以通过后台来指定


2.html
	九宫格抽奖
	使用方法：
		1.引入jquery、logttery2.js
		2.在页面中初始化lottery.init('lottery');
		3.默认8个奖品，从左上角index为0，顺时针分别为0,1,2,3,4,5,6,7,8, 对应class为lottery-unit-index
		4.点击抽奖按钮后执行 roll();并可以通过 lottery.num指定最后要停在的位置。
		  此时可选参数为
		  index:5,	//当前转动到哪个位置，起点位置
		  speed:20,	//初始转动速度
		  times:0,	//转动次数
		  cycle:20,	//转动基本次数：即至少需要转动多少次再进入抽奖环节
		  num:6,    //最后停下的位置
		  在实际开发中可能只需要从后台取到抽奖结果，然后赋值给lottery.num即可。
		5.为防止用户多次点击抽奖，有一个click参数，默认为false，可以像下面这样使用
			$("#lottery a").click(function(){
				if (click) {
					return false;
				}else{
					click=true;
					lottery.speed=100;
					lottery.num=1;//最后停的位置
					roll();
					return false;
				}
			});
