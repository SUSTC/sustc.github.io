# 校园巴士 - 节假日

## 欣园 → 科研楼（共46班）

* 欣园⇋慧园⇋创园⇋荔园⇋教工餐厅→社康中心→专家公寓⇋三号门⇋一号门⇋行政楼⇋七号门⇋科研楼

{% raw %}

<div id="bus-table-hl2rb">
    <table class="dataTable" id="work-bus-hl2rb">
    </table>
</div>

<script type="text/javascript">
    var busdata_hl2rb= [
        ["07:00","",""],
        ["07:20","",""],
        ["07:40","",""],
        ["08:00","",""],
        ["08:20","",""],
        ["08:40","",""],
        ["09:00","",""],
        ["09:20","",""],
        ["09:40","",""],
        ["10:00","",""],
        ["10:20","",""],
        ["10:40","",""],
        ["11:00","",""],
        ["11:20","",""],
        ["11:40","",""],
        ["12:00","",""],
        ["12:20","",""],
        ["12:40","",""],
        ["13:00","",""],
        ["13:20","",""],
        ["13:40","",""],
        ["14:00","",""],
        ["14:20","",""],
        ["14:40","",""],
        ["15:00","",""],
        ["15:20","",""],
        ["15:40","",""],
        ["16:00","",""],
        ["16:20","",""],
        ["16:40","",""],
        ["17:00","",""],
        ["17:20","",""],
        ["17:40","",""],
        ["18:00","",""],
        ["18:20","",""],
        ["18:40","",""],
        ["19:00","",""],
        ["19:20","",""],
        ["19:40","",""],
        ["20:00","",""],
        ["20:20","",""],
        ["20:40","",""],
        ["21:00","",""],
        ["21:20","",""],
        ["21:40","",""],
        ["22:00","",""],
    ];
    var busdata_rb2hl = [
        ["07:20","",""],
        ["07:40","",""],
        ["08:00","",""],
        ["08:20","",""],
        ["08:40","",""],
        ["09:00","",""],
        ["09:20","",""],
        ["09:40","",""],
        ["10:00","",""],
        ["10:20","",""],
        ["10:40","",""],
        ["11:00","",""],
        ["11:20","",""],
        ["11:40","",""],
        ["12:00","",""],
        ["12:20","",""],
        ["12:40","",""],
        ["13:00","",""],
        ["13:20","",""],
        ["13:40","",""],
        ["14:00","",""],
        ["14:20","",""],
        ["14:40","",""],
        ["15:00","",""],
        ["15:20","",""],
        ["15:40","",""],
        ["16:00","",""],
        ["16:20","",""],
        ["16:40","",""],
        ["17:00","",""],
        ["17:20","",""],
        ["17:40","",""],
        ["18:00","",""],
        ["18:20","",""],
        ["18:40","",""],
        ["19:00","",""],
        ["19:20","",""],
        ["19:40","",""],
        ["20:00","",""],
        ["20:20","",""],
        ["20:40","",""],
        ["21:00","",""],
        ["21:20","",""],
        ["21:40","",""],
        ["22:00","",""],
        ["22:20","",""],
    ];
    function getTime(MinBefore) {
        var date = new Date();
        date.setMinutes(date.getMinutes() - MinBefore);
        var h = date.getHours();
        var hour = (h < 10) ? "0" + h : h;
        var m = date.getMinutes();
        var min = (m < 10) ? "0" + m : m;
        return hour + ":" + min;
    }
    var now_20 = getTime(20);
    var now = getTime(0);

    var now_bus_row_hl2rb = 0;
    for(var i = 0, len = busdata_hl2rb.length; i < len; i++){
        if (busdata_hl2rb[i][0] < now_20) {
            busdata_hl2rb[i][2] = "已到达";
            now_bus_row_hl2rb = i;
        }else if (busdata_hl2rb[i][0] < now) {
            busdata_hl2rb[i][2] = "在途中";
        }else{
            busdata_hl2rb[i][2] = "未发车";
        }
    }

</script>

{% endraw %}

## 科研楼 → 欣园（共46班）

{% raw %}
<div id="bus-table-rb2hl">
    <table class="dataTable" id="work-bus-rb2hl">
    </table>
</div>

<script type="text/javascript">
    var now_bus_row_rb2hl = 0;
    for(var i = 0, len = busdata_rb2hl.length; i < len; i++){
        if (busdata_rb2hl[i][0] < now_20) {
            busdata_rb2hl[i][2] = "已到达";
            now_bus_row_rb2hl = i;
        }else if (busdata_rb2hl[i][0] < now) {
            busdata_rb2hl[i][2] = "在途中";
        }else{
            busdata_rb2hl[i][2] = "未发车";
        }
    }
    
</script>
{% endraw %}


## 参考文献
* 2019年9月29日 `校园服务办公室 <ocs@sustech.edu.cn>` 邮件《关于调整校园巴士运行时刻及路线的通知 Notice on Adjustment of Campus Bus Schedule and Routes【2019】39号》
    * [下载链接](./Campus_Bus_Schedule_1939.pdf)（右键 / 长按保存）

* 2019年8月30日 `校园服务办公室 <ocs@sustech.edu.cn>` 邮件《关于调整校园巴士运行时刻及路线的通知 Notice on Adjustment of Campus Bus Schedule and Routes【2019】30号》
    * [下载链接](./Campus_Bus_Schedule_1930.pdf)（右键 / 长按保存）

* 2019年5月16日 `校园服务办公室 <ocs@sustech.edu.cn>` 邮件《关于调整校园巴士运行时刻的通知 Notification about Adjustments of the Campus Bus Schedule【2019】12号》
    * [下载链接](./Campus_Bus_Schedule_1912.pdf)（右键 / 长按保存）

* 2018年12月29日 `校园服务办公室 <ocs@sustc.edu.cn>` 邮件《关于调整校园巴士运行时刻的通知 Notification about Adjustments of the Campus Bus Schedule【2018】50号》
    * [下载链接](./Campus_Bus_Schedule_1850.pdf)（右键 / 长按保存）

* 2018年9月29日 `校园服务办公室 <ocs@sustc.edu.cn>` 邮件《通知：调整校园巴士运行时刻 Notification: Adjustments of the Campus Bus Schedule【2018】31号》
    * [下载链接](./Campus_Bus_Schedule_1831.pdf)（右键 / 长按保存）