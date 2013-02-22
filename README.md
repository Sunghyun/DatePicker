![Screenshot](https://raw.github.com/luminousman/DatePicker/master/screenshot.png)

``` java
@Override
	public void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.main);

		DatePicker d = (DatePicker) findViewById(R.id.datePicker1);
		d.setDateChangedListener(this);

		try {
			d.setStartYear(2000);
			d.setEndYear(2009);
		} catch (Exception e) {
			Log.e("", e.toString());
		}

		TimePicker t = (TimePicker) findViewById(R.id.timePicker2);
		t.setTimeChangedListener(this);
		t.setCurrentTimeFormate(TimePicker.HOUR_12);
		t.setAMPMVisible(true);
	}

	@Override
	public void onDateChanged(Calendar c) {
		Log.e("",
				"" + c.get(Calendar.MONTH) + " " + c.get(Calendar.DAY_OF_MONTH)
						+ " " + c.get(Calendar.YEAR));
	}

	@Override
	public void onTimeChanged(int h, int m, int am_pm) {
		Log.e("", "" + h + " " + m + " " + am_pm);
	}
```