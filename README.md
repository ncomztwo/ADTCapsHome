<script>
    // record start time
    var startTime;

    function display() {
        // later record end time
        var endTime = new Date();

        // time difference in ms
        var timeDiff = endTime - startTime;

        // strip the miliseconds
        timeDiff /= 1000;

        var seconds = Math.round(timeDiff % 60);
        timeDiff = Math.floor(timeDiff / 60);
        var minutes = Math.round(timeDiff % 60);
        timeDiff = Math.floor(timeDiff / 60);
        var hours = Math.round(timeDiff % 24);
        timeDiff = Math.floor(timeDiff / 24);
        var days = timeDiff;

        if (hours < 10)   { hours = "0" + hours; }
        if (minutes < 10) { minutes = "0" + minutes; }
        if (seconds < 10) { seconds  = "0" + seconds; }

        if(days >= 1) {
            $("#reloadPage").show();
        }
        else {
            $("#reloadPage").hide();
        }

        if(timeDiff >= 0) {
            $(".time").text("("+ days + " days, " + hours + ":" + minutes + ":" + seconds + " passed since last release.)");
        }
        setTimeout(display, 1000);
    }

    function elapsedTimerStart () {
        //startTime = new Date();
        //setTimeout(display, 1000);

        var text = $("#releaseTime").text();
        var year = text.substring(0, 4);
        var month = text.substring(5, 7);
        var date = text.substring(8, 10);
        var hour = text.substring(11, 13);
        var min = text.substring(14, 16);
        //alert(year+" "+month+" "+date+" "+hour+" "+min);

        startTime = new Date(year, month-1, date, hour, min, 0, 0);
        display();
    }
</script>

# Android ADT_캡스홈

## Version  :  0.1.0.1
<font color="#BDBDBD">2016-09-29 14:00</font><br> 
<p id="reloadPage">Click <a href="javascript:location.reload();">here</a> to reload this page.</p>

###배포 Version

click [** HERE **](https://github.com/ncomztwo/ADTCapsHome/raw/master/Release_Version/ADTCapsHomeService.apk) to install the app.

###Test Version

click [** HERE **](https://github.com/ncomztwo/ADTCapsHome/raw/master/Test_Version/ADTCapsHomeService.apk) to install the app.