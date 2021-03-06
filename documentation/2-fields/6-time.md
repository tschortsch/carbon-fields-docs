# Time

Renders a time picker field.

`Field::make('time', 'opens_at', 'Opening time')`

### Setup Methods

`set_time_format` **(string)**

Sets the time format in which to display and save the time values.

Here is a list of allowed Format Characters:

----------------------------------------------------------
|Character|Definition                          | Examples|
|:-------:|------------------------------------|--------:|
|**Time** |                                    |         |
|t        |Lowercase                           |     a, p|
|T        |Lowercase                           |     A, P|
|tt       |Lowercase                           |   am, pm|
|TT       |Uppercase                           |   AM, PM|
|h        |Hour, 12-hour, without leading zeros|     1-12|
|hh       |Hour, 12-hour, with leading zeros   |    01-12|
|H        |Hour, 24-hour, without leading zeros|     0-23|
|HH       |Hour, 24-hour, with leading zeros   |    00-23|
|m        |Minutes, without leading zeros      |     0-59|
|mm       |Minutes, with leading zeros         |    00-59|
|s        |Seconds, without leading zeros      |     0-59|
|ss       |Seconds, with leading zeros         |    00-59|

	Field::make('time', 'time', 'Time')
		->set_time_format('hh:mm:ss tt')

----
`set_interval_step` **(array)**

Sets the interval step for *hours*, *minutes* and *seconds*.

	Field::make('time', 'time', 'Time')
		->set_interval_step(array(
			'hour'   => '2',
			'minute' => '10',
			'second' => '10',
		))

----
`set_restraints` **(array)**

Sets restraints for *Hours*, *Minutes*, *Seconds*.

|Type            |Definition                                     |Default  |
|:--------------:|-----------------------------------------------|--------:|
|**Hours**       |                                               |         |
|hourMin         |The minimum hour allowed for all dates         |        0|
|hourMax         |The maximum hour allowed for all dates         |       23|
|**Minutes**     |                                               |         |
|minuteMin       |The minimum minute allowed for all dates       |        0|
|minuteMax       |The maximum minute allowed for all dates       |       59|
|**Seconds**     |                                               |         |
|secondMin       |The minimum second allowed for all dates       |        0|
|secondMax       |The maximum second allowed for all dates       |       59|
|**Milliseconds**|                                               |         |
|millisecMin     |The minimum millisecond allowed for all dates  |        0|
|millisecMax     |The maximum millisecond allowed for all dates  |      999|
|**Microsec**    |                                               |         |
|microsecMin     |The minimum microsecond allowed for all dates  |        0|
|microsecMax     |The maximum microsecond allowed for all dates  |      999|

	Field::make('time', 'time', 'Time')
		->set_restraints(array(
			'hourMin' => '9',
			'hourMax' => '18',
		))

----
`set_timepicker_options` **(array)**

With this method you can set other time picker options. 

	Field::make('time', 'time', 'Time')
		->set_timepicker_options(array(
			'currentText' => 'Current time',
		))
	
You can find a full list of all available options here: 

 * [Timepicker options](http://trentrichardson.com/examples/timepicker/#tp-options)
