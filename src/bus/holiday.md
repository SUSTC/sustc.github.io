# 校园巴士 - 节假日


## 欣园 → 科研楼（共27班）

* 欣园⇋慧园⇋创园⇋荔园⇋教工餐厅→社康中心→专家公寓⇋三号门⇋一号门⇋行政楼⇋七号门⇋科研楼

{% raw %}
<script src="https://cdn.bootcss.com/jquery/3.3.1/jquery.min.js"></script>
<script src="https://cdn.bootcss.com/datatables/1.10.19/js/jquery.dataTables.min.js"></script>
<link href="https://cdn.bootcss.com/datatables/1.10.19/css/jquery.dataTables.min.css" rel="stylesheet">

<div id="bus-table-hl2rb">
    <table class="dataTable" id="work-bus-hl2rb">
    </table>
</div>

<script type="text/javascript">
    var busdata_hl2rb= [
        ["07:30","",""],
        ["08:00","",""],
        ["08:30","",""],
        ["09:00","",""],
        ["09:30","",""],
        ["10:00","",""],
        ["10:30","",""],
        ["11:00","",""],
        ["11:30","",""],
        ["12:00","",""],
        ["12:30","",""],
        ["13:00","",""],
        ["13:30","",""],
        ["14:00","",""],
        ["14:30","",""],
        ["15:00","",""],
        ["15:30","",""],
        ["16:00","",""],
        ["16:30","",""],
        ["17:00","",""],
        ["17:30","",""],
        ["18:00","",""],
        ["18:30","",""],
        ["19:00","",""],
        ["20:00","",""],
        ["21:00","",""],
        ["21:40","",""],
    ];
    var busdata_rb2hl = [
        ["07:50","",""],
        ["08:20","",""],
        ["08:50","",""],
        ["09:20","",""],
        ["09:50","",""],
        ["10:20","",""],
        ["10:50","",""],
        ["11:20","",""],
        ["11:50","",""],
        ["12:20","",""],
        ["12:50","",""],
        ["13:20","",""],
        ["13:50","",""],
        ["14:20","",""],
        ["14:50","",""],
        ["15:20","",""],
        ["15:50","",""],
        ["16:20","",""],
        ["16:50","",""],
        ["17:20","",""],
        ["17:50","",""],
        ["18:20","",""],
        ["19:20","",""],
        ["20:20","",""],
        ["21:20","",""],
        ["22:00","",""],
        ["22:10","",""],
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
    var ins_table_hl2rb = $('#work-bus-hl2rb').DataTable( {
        data: busdata_hl2rb,
        scrollY: 300,
        paging: false,
        searching : false,
        bFilter: false,
        info: false,
        columns: [
            { title: "发车时间" },
            { title: "平时/高峰", "orderable": false },
            { title: "状态", "orderable": false },
        ],
        rowCallback: function( row, data, index ) {
            if ( data[2] == "已到达" )
            {
                $('td', row).css('background-color', '#003f43'); // SUSTech dark green
                $('td', row).css('color', '#FFFFFF');
            }
            else if ( data[2] == "在途中" )
            {
                $('td', row).css('background-color', '#ed6c00'); // SUSTech orange
                $('td', row).each(function(){
                    $(this).html( '<b>'+$(this).text()+'</b>');
                });
            }
        }
    } );
    var now_bus_offset =$(ins_table_hl2rb.row(Math.min(now_bus_row_hl2rb, busdata_hl2rb.length)).node()).offset().top - $(ins_table_hl2rb.row(0).node()).offset().top;
    $("#bus-table-hl2rb .dataTables_scrollBody").scrollTop(now_bus_offset);

</script>

{% endraw %}

## 科研楼 → 欣园（共27班）

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
    var ins_table_rb2hl = $('#work-bus-rb2hl').DataTable( {
        data: busdata_rb2hl,
        scrollY: 300,
        paging: false,
        searching : false,
        bFilter: false,
        info: false,
        columns: [
            { title: "发车时间" },
            { title: "平时/高峰", "orderable": false },
            { title: "状态", "orderable": false },
        ],
        rowCallback: function( row, data, index ) {
            if ( data[2] == "已到达" )
            {
                $('td', row).css('background-color', '#003f43'); // SUSTech dark green
                $('td', row).css('color', '#FFFFFF');
            }
            else if ( data[2] == "在途中" )
            {
                $('td', row).css('background-color', '#ed6c00'); // SUSTech orange
                $('td', row).each(function(){
                    $(this).html( '<b>'+$(this).text()+'</b>');
                });
            }
        }
    } );
    var now_bus_offset =$(ins_table_rb2hl.row(Math.min(now_bus_row_rb2hl, busdata_rb2hl.length)).node()).offset().top - $(ins_table_rb2hl.row(0).node()).offset().top;
    $("#bus-table-rb2hl .dataTables_scrollBody").scrollTop(now_bus_offset);
</script>
{% endraw %}

## 荔园 → 集悦城（共10班）

* 荔园→慧园→行政楼→七号门→集悦城B区站→集悦城A区站
    * 集悦城A区停车点位于留仙大道辅道（塘朗山隧道路口公交站）

{% raw %}
<div id="bus-table-lh2jyc">
    <table class="dataTable" id="work-bus-lh2jyc">
    </table>
</div>

<script type="text/javascript">
    var busdata_lh2jyc = [
        ["12:00","",""],
        ["12:40","",""],
        ["13:40","",""],
        ["18:40","",""],
        ["19:00","",""],
        ["19:40","",""],
        ["20:20","",""],
        ["21:00","",""],
        ["21:40","",""],
        ["22:30","",""],
    ];
    var now_bus_row_lh2jyc = 0;
    for(var i = 0, len = busdata_lh2jyc.length; i < len; i++){
        if (busdata_lh2jyc[i][0] < now_20) {
            busdata_lh2jyc[i][2] = "已到达";
            now_bus_row_lh2jyc = i;
        }else if (busdata_lh2jyc[i][0] < now) {
            busdata_lh2jyc[i][2] = "在途中";
        }else{
            busdata_lh2jyc[i][2] = "未发车";
        }
    }
    var ins_table_lh2jyc = $('#work-bus-lh2jyc').DataTable( {
        data: busdata_lh2jyc,
        scrollY: 300,
        paging: false,
        searching : false,
        bFilter: false,
        info: false,
        columns: [
            { title: "发车时间" },
            { title: "平时/高峰", "orderable": false },
            { title: "状态", "orderable": false },
        ],
        rowCallback: function( row, data, index ) {
            if ( data[2] == "已到达" )
            {
                $('td', row).css('background-color', '#003f43'); // SUSTech dark green
                $('td', row).css('color', '#FFFFFF');
            }
            else if ( data[2] == "在途中" )
            {
                $('td', row).css('background-color', '#ed6c00'); // SUSTech orange
                $('td', row).each(function(){
                    $(this).html( '<b>'+$(this).text()+'</b>');
                });
            }
        }
    } );
    var now_bus_offset =$(ins_table_lh2jyc.row(Math.min(now_bus_row_lh2jyc, busdata_lh2jyc.length)).node()).offset().top - $(ins_table_lh2jyc.row(0).node()).offset().top;
    $("#bus-table-lh2jyc .dataTables_scrollBody").scrollTop(now_bus_offset);
</script>
{% endraw %}

## 集悦城 → 荔园（共10班）

* 集悦城B区站→集悦城A区站→六号门→荔园→慧园
    * 集悦城B区停车点位于集悦城A19栋

{% raw %}
<div id="bus-table-jyc2lh">
    <table class="dataTable" id="work-bus-jyc2lh">
    </table>
</div>

<script type="text/javascript">
    var busdata_jyc2lh = [
        ["07:20","",""],
        ["08:00","",""],
        ["08:40","",""],
        ["09:20","",""],
        ["10:40","",""],
        ["11:20","",""],
        ["12:20","",""],
        ["13:20","",""],
        ["14:00","",""],
        ["15:20","",""],
    ];
    var now_bus_row_jyc2lh = 0;
    for(var i = 0, len = busdata_jyc2lh.length; i < len; i++){
        if (busdata_jyc2lh[i][0] < now_20) {
            busdata_jyc2lh[i][2] = "已到达";
            now_bus_row_jyc2lh = i;
        }else if (busdata_jyc2lh[i][0] < now) {
            busdata_jyc2lh[i][2] = "在途中";
        }else{
            busdata_jyc2lh[i][2] = "未发车";
        }
    }
    var ins_table_jyc2lh = $('#work-bus-jyc2lh').DataTable( {
        data: busdata_jyc2lh,
        scrollY: 300,
        paging: false,
        searching : false,
        bFilter: false,
        info: false,
        columns: [
            { title: "发车时间" },
            { title: "平时/高峰", "orderable": false },
            { title: "状态", "orderable": false },
        ],
        rowCallback: function( row, data, index ) {
            if ( data[2] == "已到达" )
            {
                $('td', row).css('background-color', '#003f43'); // SUSTech dark green
                $('td', row).css('color', '#FFFFFF');
            }
            else if ( data[2] == "在途中" )
            {
                $('td', row).css('background-color', '#ed6c00'); // SUSTech orange
                $('td', row).each(function(){
                    $(this).html( '<b>'+$(this).text()+'</b>');
                });
            }
        }
    } );
    var now_bus_offset =$(ins_table_jyc2lh.row(Math.min(now_bus_row_jyc2lh, busdata_jyc2lh.length)).node()).offset().top - $(ins_table_jyc2lh.row(0).node()).offset().top;
    $("#bus-table-jyc2lh .dataTables_scrollBody").scrollTop(now_bus_offset);
</script>
{% endraw %}

## 参考文献

* 2018年12月29日 `校园服务办公室 <ocs@sustc.edu.cn>` 邮件《关于调整校园巴士运行时刻的通知 Notification about Adjustments of the Campus Bus Schedule【2018】50号》
    * [下载链接](./Campus_Bus_Schedule_1850.pdf)（右键 / 长按保存）

* 2018年9月29日 `校园服务办公室 <ocs@sustc.edu.cn>` 邮件《通知：调整校园巴士运行时刻 Notification: Adjustments of the Campus Bus Schedule【2018】31号》
    * [下载链接](./Campus_Bus_Schedule_1831.pdf)（右键 / 长按保存）