# 校园巴士

{% raw %}

<div id="tag-div">
    <span id="tag">
    </span>
</div>

<div id="button-div">
    <a href="./workday.html" class="button size-2">工作日</a>
    <a href="./holiday.html" class="button size-2">节假日</a>
</div>


<script type="text/javascript">
    var showTime = function(jumpTime, url, message) {
        document.getElementById("tag").innerHTML= jumpTime + message;
        if(jumpTime==0){
            location.href=url;
        }
        jumpTime -= 1;
        setTimeout(function() { showTime(jumpTime, url, message); }, 1000);
    };
    var date = new Date().getDay();
    var isWeekend = (date == 6) || (date == 0);    // 6 = Saturday, 0 = Sunday
    if (isWeekend){
        showTime(5, "./holiday.html", "秒后自动跳转到节假日。点击下方按钮手动跳转。");
    }else{
        showTime(5, "./workday.html", "秒后自动跳转到工作日。点击下方按钮手动跳转。");
    }
</script>

{% endraw %}