# localStorage赋值
解决方案：关于localStorage赋值，并不是一个指向这个获取到的键值的指针

        var storage = window.localStorage,
            defense = storage.getItem("defense");

        defense.setItem("defense", "true");

        console.log(defense); // true

        if(defense){
            storage.removeItem("defense");

            console.lgo(defense); // true
            console.lgo(storage.getItem("defense")); // null
        }

#Android手机，input获取焦点后，页面弹不起来
解决方案：给容器加上高度并绝对定位在底部

        var h = window.innerHeight;

        $(".main").css("height", h);
    
#页面回退ajax请求的数据不更新
解决方案：在ajax请求url上加时间戳

        var time = new Date().getTime();

        $.ajax({
            url: "?ver=" + time,
            success: function(){}
        });
    
#iphone4下，input获取焦点，输入框有时不会自动上移
解决方案：添加js控制，需要给iPhone4专门加上过滤条件，不然其他类型iPhone的手机会连续滚动两次 

        var h = window.innerHeight;
        $("#mobile").on("focus", function(){
            var $this = $(this);
            if(window.innerHeight < h){ // 过滤条件 
                $("html,body").animate({scrollTop: $this.offset().top},1000);
            }
        });
    
    
