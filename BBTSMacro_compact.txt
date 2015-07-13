// r/BigBrother Live Feed Time Stamp RES Custom Macro (compacted code, no comments)
// by /u/firehazard07
// version: 3.43	/	last updated: 7/13/2015 @ 05:08 AM PST	/	73 lines with comments
this.addButtonToMacroGroup('', this.makeEditButton('BBT ts v3.43', '', null, 'btn-macro btn-bbt-timestamp', function(button, box) {
	var d = new Date();
	var utc = d.getTime() + (d.getTimezoneOffset() * 60000);
	var nd = new Date(utc + (3600000 * (-7)));
	var weekday = new Array(7);
		weekday[0] = "SUN";
		weekday[1] = "MON";
		weekday[2] = "TUE";
		weekday[3] = "WED";
		weekday[4] = "THU";
		weekday[5] = "FRI";
		weekday[6] = "SAT";
	var day = weekday[nd.getDay()];
	var month = nd.getMonth();
	    month = month + 1;
	var date = nd.getDate();
	var hour = nd.getHours();
	var daytime = new Array(3);
		daytime[0] = " ";
		daytime[1] = "AM";
		daytime[2] = "PM";
	var AMPM = daytime[0];
	if (hour > 12) {
		hour = hour - 12;
		AMPM = daytime[2];
		}
	else AMPM = daytime[1];
	function addZero(i) {
		if (i < 10) {i = "0" + i;}
		return i;
		}
	var h = addZero(hour);
	var m = addZero(nd.getMinutes());
	var s = addZero(nd.getSeconds());		
	this.macroSelection(box, '\n**\\#TS** : ' + day.toString() + ' ' + month.toString() + '\/' + date.toString() + ' @ **' + h.toString() + ':' + m.toString() + ':' + s.toString() + ' ' + AMPM.toString() + '** PST/BBT, CAM ? \n\n> ');
}));
// </>