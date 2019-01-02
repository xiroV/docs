<html>
<head>
</head>

<body>
<h1>JolieDoc for Port Time</h1>
<h2>General description</h2>
<pre>
This native service allows the manipulation of DateTime data type with the its typical operations
</pre>
<h2>From file <code>time.iol
</code></h2>
<table>
<tr>
<th>Port Name</th>
<th>Location</th>
<th>Protocol</th>
</tr>
<tr>
<td>Time</td>
<td></td>
<td></td>
</tr>
</table>
<h2>List of the available interfaces</h2>
<ul>
<li><a href="#TimeInterface">TimeInterface </a>
</ul>
<hr>
<h2 id=TimeInterface>Interface TimeInterface</h2>
<a name="TimeInterface"></a>
<table border="1">
<tr>
<th>Heading</th>
<th>Input type</th>
<th>Output type</th>
<th>Faults</th>
</tr>
<tr>
<td><a href="#cancelTimeout">cancelTimeout</a></td>
<td>long<br /></td>
<td>bool<br /></td>
<td>
</td>
</tr>
<tr>
<td><a href="#getCurrentDateTime">getCurrentDateTime</a></td>
<td><a href="#CurrentDateTimeRequestType">CurrentDateTimeRequestType</a><br /></td>
<td>string<br /></td>
<td>
</td>
</tr>
<tr>
<td><a href="#getCurrentDateValues">getCurrentDateValues</a></td>
<td>void<br /></td>
<td><a href="#DateValuesType">DateValuesType</a><br /></td>
<td>
</td>
</tr>
<tr>
<td><a href="#getCurrentTimeMillis">getCurrentTimeMillis</a></td>
<td>void<br /></td>
<td>long<br /></td>
<td>
</td>
</tr>
<tr>
<td><a href="#getDateDiff">getDateDiff</a></td>
<td><a href="#DiffDateRequestType">DiffDateRequestType</a><br /></td>
<td>int<br /></td>
<td>
</td>
</tr>
<tr>
<td><a href="#getDateTime">getDateTime</a></td>
<td><a href="#GetDateTimeRequest">GetDateTimeRequest</a><br /></td>
<td><a href="#GetDateTimeResponse">GetDateTimeResponse</a><br /></td>
<td>
</td>
</tr>
<tr>
<td><a href="#getDateTimeValues">getDateTimeValues</a></td>
<td><a href="#GetTimestampFromStringRequest">GetTimestampFromStringRequest</a><br /></td>
<td><a href="#DateTimeType">DateTimeType</a><br /></td>
<td>
InvalidDate,&nbsp;<br>
</td>
</tr>
<tr>
<td><a href="#getDateValues">getDateValues</a></td>
<td><a href="#DateValuesRequestType">DateValuesRequestType</a><br /></td>
<td><a href="#DateValuesType">DateValuesType</a><br /></td>
<td>
InvalidDate,&nbsp;<br>
</td>
</tr>
<tr>
<td><a href="#getTimeDiff">getTimeDiff</a></td>
<td><a href="#GetTimeDiffRequest">GetTimeDiffRequest</a><br /></td>
<td>int<br /></td>
<td>
</td>
</tr>
<tr>
<td><a href="#getTimeFromMilliSeconds">getTimeFromMilliSeconds</a></td>
<td>int<br /></td>
<td><a href="#TimeValuesType">TimeValuesType</a><br /></td>
<td>
</td>
</tr>
<tr>
<td><a href="#getTimeValues">getTimeValues</a></td>
<td>string<br /></td>
<td><a href="#TimeValuesType">TimeValuesType</a><br /></td>
<td>
</td>
</tr>
<tr>
<td><a href="#getTimestampFromString">getTimestampFromString</a></td>
<td><a href="#GetTimestampFromStringRequest">GetTimestampFromStringRequest</a><br /></td>
<td>long<br /></td>
<td>
InvalidTimestamp,&nbsp;<br>
</td>
</tr>
<tr>
<td><a href="#scheduleTimeout">scheduleTimeout</a></td>
<td><a href="#ScheduleTimeOutRequest">ScheduleTimeOutRequest</a><br /></td>
<td>long<br /></td>
<td>
InvalidTimeUnit,&nbsp;<br>
</td>
</tr>
<tr>
<td><a href="#setNextTimeout">setNextTimeout</a></td>
<td><a href="#SetNextTimeOutRequest">SetNextTimeOutRequest</a><br /></td><td>&nbsp;</td><td>&nbsp;</td>
</tr>
</tr>
<tr>
<td><a href="#setNextTimeoutByDateTime">setNextTimeoutByDateTime</a></td>
<td><a href="#undefined">undefined</a><br /></td><td>&nbsp;</td><td>&nbsp;</td>
</tr>
</tr>
<tr>
<td><a href="#setNextTimeoutByTime">setNextTimeoutByTime</a></td>
<td><a href="#undefined">undefined</a><br /></td><td>&nbsp;</td><td>&nbsp;</td>
</tr>
</tr>
<tr>
<td><a href="#sleep">sleep</a></td>
<td>undefined<br /></td>
<td>undefined<br /></td>
<td>
</td>
</tr>
</table>
<hr>
<h2>Operation list</h2>
<div class="operation-title"><a name="scheduleTimeout"></a><h3 id="scheduleTimeout">scheduleTimeout</h3></div>
<pre>scheduleTimeout( <a href="#ScheduleTimeOutRequest">ScheduleTimeOutRequest</a> )( <a href="#long">long</a> )
 throws

				
InvalidTimeUnit
</pre>
<span class="opdoc"><p>It set a programmable scheduled timeout that allows to call a specific operation when a timeout is triggered <a href="#scheduleTimeoutFullExample">see full example</a></p></span>

<div class="operation-title"><a name="getDateValues"></a><h3 id="getDateValues">getDateValues</h3></div>
<pre>getDateValues( <a href="#DateValuesRequestType">DateValuesRequestType</a> )( <a href="#DateValuesType">DateValuesType</a> )
 throws

				
InvalidDate
</pre>
<span class="opdoc"><p>Converts an input string into a date expressed by means of<br>		 three elements: day, month and year. The request may specify the<br>		 date parsing format. See #DateValuesRequestType for details.</p></span>
<div class="operation-title"><a name="getDateTime"></a><h3 id="getDateTime">getDateTime</h3></div>
<pre>getDateTime( <a href="#GetDateTimeRequest">GetDateTimeRequest</a> )( <a href="#GetDateTimeResponse">GetDateTimeResponse</a> )
</pre>
<span class="opdoc"><p>It returns a date time in a string format starting from a timestamp</p></span>
<div class="operation-title"><a name="getCurrentTimeMillis"></a><h3 id="getCurrentTimeMillis">getCurrentTimeMillis</h3></div>
<pre>getCurrentTimeMillis( <a href="#void">void</a> )( <a href="#long">long</a> )
</pre>
<span class="opdoc"><p>Warning: this is temporary and subject to future change as soon as long is supported by Jolie.</p></span>
<div class="operation-title"><a name="getDateDiff"></a><h3 id="getDateDiff">getDateDiff</h3></div>
<span class="opdoc"><p>It returns a date differance expessed in milliseconds  </p></span>
<pre>getDateDiff( <a href="#DiffDateRequestType">DiffDateRequestType</a> )( <a href="#int">int</a> )
</pre>

<div class="operation-title"><a name="getTimeDiff"></a><h3 id="getTimeDiff">getTimeDiff</h3></div>
<span class="opdoc"><p>It returns a time differance expessed in milliseconds  </p></span>
<pre>getTimeDiff( <a href="#GetTimeDiffRequest">GetTimeDiffRequest</a> )( <a href="#int">int</a> )
</pre>
<div class="operation-title"><a name="getTimestampFromString"></a><h3 id="getTimestampFromString">getTimestampFromString</h3></div>
<pre>getTimestampFromString( <a href="#GetTimestampFromStringRequest">GetTimestampFromStringRequest</a> )( <a href="#long">long</a> )
 throws

				
InvalidTimestamp
</pre>
<div class="operation-title"><a name="cancelTimeout"></a><h3 id="cancelTimeout">cancelTimeout</h3></div>
<pre>cancelTimeout( <a href="#long">long</a> )( <a href="#bool">bool</a> )
</pre>
<span class="opdoc"><p>Cancels a timeout from a long-value created from #scheduleTimeout</p></span>
<div class="operation-title"><a name="setNextTimeoutByTime"></a><h3 id="setNextTimeoutByTime">setNextTimeoutByTime</h3></div>
<p><pre>setNextTimeoutByTime( <a href="#undefined">undefined</a> )</pre></p>
<div class="operation-title"><a name="getCurrentDateTime"></a><h3 id="getCurrentDateTime">getCurrentDateTime</h3></div>
<pre>getCurrentDateTime( <a href="#CurrentDateTimeRequestType">CurrentDateTimeRequestType</a> )( <a href="#string">string</a> )
</pre>
<div class="operation-title"><a name="sleep"></a><h3 id="sleep">sleep</h3></div>
<pre>sleep( <a href="#undefined">undefined</a> )( <a href="#undefined">undefined</a> )
</pre>
<div class="operation-title"><a name="setNextTimeout"></a><h3 id="setNextTimeout">setNextTimeout</h3></div>
<p><pre>setNextTimeout( <a href="#SetNextTimeOutRequest">SetNextTimeOutRequest</a> )</pre></p>
<span class="opdoc"><p>It set a programmable timeout that allows to call a specific operation when a timeout is triggered
 <a href="#setNextTimeoutFullExmpla">see full example</a></p></span>
<div class="operation-title"><a name="getTimeFromMilliSeconds"></a><h3 id="getTimeFromMilliSeconds">getTimeFromMilliSeconds</h3></div>
<pre>getTimeFromMilliSeconds( <a href="#int">int</a> )( <a href="#TimeValuesType">TimeValuesType</a> )
</pre>
<div class="operation-title"><a name="getDateTimeValues"></a><h3 id="getDateTimeValues">getDateTimeValues</h3></div>
<pre>getDateTimeValues( <a href="#GetTimestampFromStringRequest">GetTimestampFromStringRequest</a> )( <a href="#DateTimeType">DateTimeType</a> )
 throws

				
InvalidDate
</pre>
<div class="operation-title"><a name="setNextTimeoutByDateTime"></a><h3 id="setNextTimeoutByDateTime">setNextTimeoutByDateTime</h3></div>
<p><pre>setNextTimeoutByDateTime( <a href="#undefined">undefined</a> )</pre></p>
<div class="operation-title"><a name="getCurrentDateValues"></a><h3 id="getCurrentDateValues">getCurrentDateValues</h3></div>
<pre>getCurrentDateValues( <a href="#void">void</a> )( <a href="#DateValuesType">DateValuesType</a> )
</pre>
<span class="opdoc"><p>Returns the current date split in three fields: day, month and year</p></span>
<div class="operation-title"><a name="getTimeValues"></a><h3 id="getTimeValues">getTimeValues</h3></div>
<pre>getTimeValues( <a href="#string">string</a> )( <a href="#TimeValuesType">TimeValuesType</a> )
</pre>
<hr>
<h2>Message type list</h2>
<a name="ScheduleTimeOutRequest"></a><h3 id="ScheduleTimeOutRequest">ScheduleTimeOutRequest</h3>
<pre lang="jolie">type ScheduleTimeOutRequest: int { 
    .message?: undefined
    .operation?: string
    .timeunit?: string
}</pre>

<span class="opdoc">
<p>The <b>root</b> value rapresents the interval in timeunit after which the timeout is triggered</p> 
<p>The  node <b>timeunit</b> expresses represents time durations at a given unit of granularity using the <a href="https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/TimeUnit.html"> Java TimeUnit</a> convention. If the node <b>timeunit</b>  is not defined unit is set as MILLISECONDS
<p>The node <b>operation</b> sets the operation to be call when the timeout is called. If the node <b>operation</b> is not defined the default value is set to <b>"timeout"</b> that needs to be defined and implemented in your microservice</p>
<p>
The node <b>message</b> contains the value sent to the operation
</p></span>
<a name="DateValuesRequestType"></a><h3 id="DateValuesRequestType">DateValuesRequestType</h3>
<pre lang="jolie">type DateValuesRequestType: string { 
    .format?: string
}</pre>
<a name="DateValuesType"></a><h3 id="DateValuesType">DateValuesType</h3>
<pre lang="jolie">type DateValuesType: void { 
    .month: int
    .year: int
    .day: int
}</pre>
<a name="GetDateTimeRequest"></a><h3 id="GetDateTimeRequest">GetDateTimeRequest</h3>
<pre lang="jolie">type GetDateTimeRequest: long { 
    .format?: string
}</pre>
<span class="opdoc"><p>The <b>format</b> node expresses the string format used by the operation to calculate the date <a href="https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html"> Java DateFormat</a> pattern. If the node <b>format</b>  is not defined the standard used format is "dd/MM/yyyy kk:mm:ss" </p>
</span>
<a name="GetDateTimeResponse"></a><h3 id="GetDateTimeResponse">GetDateTimeResponse</h3>
<pre lang="jolie">type GetDateTimeResponse: string { 
    .month: int  [112]
    .hour: int
    .year: int
    .day: int
    .minute: int
    .second: int
}</pre>

<a name="DiffDateRequestType"></a><h3 id="DiffDateRequestType">DiffDateRequestType</h3>
<pre lang="jolie">type DiffDateRequestType: void { 
    .format?: string
    .date2: string
    .date1: string
}</pre>
<span class="opdoc"><p>The <b>format</b> node expresses the format of the two date terms using the <a href="https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html"> Java DateFormat</a> pattern. If the node <b>format</b>  is not defined the standard used format is "dd/MM/yyyy"   </p>
<p>The operatiation will return the differance between <b>date1</b> and <b>date2</b> </p></span>
<a name="GetTimeDiffRequest"></a><h3 id="GetTimeDiffRequest">GetTimeDiffRequest</h3>
<pre lang="jolie">type GetTimeDiffRequest: void { 
    .time1: string
    .time2: string
}</pre>
<span class="opdoc"> 
<p>The nodes <b>time1</b> and <b>time2</b> are expressed as "kk:mm:ss" using the <a href="https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html"> Java DateFormat</a> patten. </p>
<p>The operatiation will return the differance between <b>time1</b> and <b>time2</b> </p></span>
</span>
<a name="GetTimestampFromStringRequest"></a><h3 id="GetTimestampFromStringRequest">GetTimestampFromStringRequest</h3>
<pre lang="jolie">type GetTimestampFromStringRequest: string { 
    .format?: string
    .language?: string
}</pre>
<span class="opdoc">
<p>The <b>root</b> value express the Timestamp as a string<p>
<p>The <b>format</b> node expresses the string format of the input Timestamp value (root value) using the <a href="https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html"> Java DateFormat</a> pattern. If the node <b>format</b>  is not defined the standard used format is "dd/MM/yyyy kk:mm:ss"  </p>
</span>

<a name="CurrentDateTimeRequestType"></a><h3 id="CurrentDateTimeRequestType">CurrentDateTimeRequestType</h3>
<pre lang="jolie">type CurrentDateTimeRequestType: void { 
    .format?: string
}</pre>
<span class="opdoc"><p>The <b>format</b> node expresses the string format of the output Timestamp value using the <a href="https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html"> Java DateFormat</a> pattern. If the node <b>format</b>  is not defined the standard used format is "dd/MM/yyyy kk:mm:ss" </p>
</span>
<a name="SetNextTimeOutRequest"></a><h3 id="SetNextTimeOutRequest">SetNextTimeOutRequest</h3>
<pre lang="jolie">type SetNextTimeOutRequest: int { 
    .message?: undefined
    .operation?: string
}</pre>
<a name="TimeValuesType"></a><h3 id="TimeValuesType">TimeValuesType</h3>
<pre lang="jolie">type TimeValuesType: void { 
    .hour: int
    .minute: int
    .second: int
}</pre>
<a name="DateTimeType"></a><h3 id="DateTimeType">DateTimeType</h3>
<pre lang="jolie">type DateTimeType: void { 
    .month: int
    .hour: int
    .year: int
    .day: int
    .minute: int
    .second: int
}</pre>
<hr>
<h2>Type list</h2>
<h3 id="undefined">undefined</h3>
<a name="undefined"></a>
<pre lang="jolie">type undefined: undefined</pre>

<h2>Example List</h2>
</body>
</html>
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk2NzQ3NzIwOSwtOTY5OTcyMTE4LC0yNT
g2NjQzODgsMjY5ODEzOTc3LC00NzQwOTIwNjAsMTAyMTczNDU3
MCwtNTM4Njg1MzUzLDEyMTQ2ODIyMDksLTQ4OTM0OTQ1NiwtMT
A4OTk2NDEwMywtNjQ2NDY0OTMwLC03NTY0OTI1NzEsLTEyNTA4
NDk0ODQsLTE2NTI5Mzk3NTEsMTg3ODk5NDE1NSwxMjIwMjc1Mz
c5LDIxMzA0NDIzOTksLTE0OTUxODIzNTIsMTk4NTg5MTY1OSw5
MTA2ODY2MTNdfQ==
-->