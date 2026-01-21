* #weekday (should not move) 
* #weekend (should not move)
* example 1:!(2023-01-27 01:30 - 2023-02-02 02:30 | ~1w)18:00i
* example 2: !(2023-03-19)@01 :30-1d@22:30r1pi
* ,,2 will put color 2, using prioritize plugin, but not sure useful
* Example
	* $$ \begin{array}{c|} \text{Header} & \text{Price} & \text{Size} & \text{When} \\ \hline \text{Item 1} & \text{2 usd} & \text{big} & \text{now} \\ \hdashline \text{Item 3} & \text{3 USD} & \text{Small} & \text{tmw} \\ \end {array} $$
	* $$ \begin{array}{c|} \text{Header} & \text{Price} & \text{Size} & \text{When} \\ \hline \text{Item 1} & \text{2 usd} & \text{big} & \text{now} \\ \hdashline \text{Item 3} & \text{3 USD} & \text{Small} & \text{tmw} \\ \end {array} $$
	* $$ \begin{array}{c|} \text{Header} & \text{Price} & \text{Size} & \text{When} \\ \hline \text{Item 1} & \text{2 usd} & \text{big} & \text{now} \\ \hdashline \text{Item 3} & \text{3 USD} & \text{Small} & \text{tmw} \\ \end {array} $$
	* $$ \begin{array}{c|} \text{Header} & \text{Price} & \text{Size} & \text{When} \\ \hline \text{Item 1} & \text{2 usd} & \text{big} & \text{now} \\ \hdashline \text{Item 3} & \text{3 USD} & \text{Small} & \text{tmw} \\ \end {array} $$
	* $$ \begin{array}{c|} \text{Header} & \text{Price} & \text{Size} & \text{When} \\ \hline \text{Item 1} & \text{2 usd} & \text{big} & \text{now} \\ \hdashline \text{Item 3} & \text{3 USD} & \text{Small} & \text{tmw} \\ \end {array} $$
	* $$ \begin{array}{c|} \text{Header} & \text{Price} & \text{Size} & \text{When} \\ \hline \text{Item 1} & \text{2 usd} & \text{big} & \text{now} \\ \hdashline \text{Item 3} & \text{3 USD} & \text{Small} & \text{tmw} \\ \end {array} $$
	* $$ \begin{array}{c|} \text{Header} & \text{Price} & \text{Size} & \text{When} \\ \hline \text{Item 1} & \text{2 usd} & \text{big} & \text{now} \\ \hdashline \text{Item 3} & \text{3 USD} & \text{Small} & \text{tmw} \\ \end {array} $$
	* $$ \begin{array}{c|} \text{Header} & \text{Price} & \text{Size} & \text{When} \\ \hline \text{Item 1} & \text{2 usd} & \text{big} & \text{now} \\ \hdashline \text{Item 3} & \text{3 USD} & \text{Small} & \text{tmw} \\ \end {array} $$
	* $$ \begin{array}{c|} \text{Header} & \text{Price} & \text{Size} & \text{When} \\ \hline \text{Item 1} & \text{2 usd} & \text{big} & \text{now} \\ \hdashline \text{Item 3} & \text{3 USD} & \text{Small} & \text{tmw} \\ \end {array} $$
	* $$ \begin{array}{c|} \text{Header} & \text{Price} & \text{Size} & \text{When} \\ \hline \text{Item 1} & \text{2 usd} & \text{big} & \text{now} \\ \hdashline \text{Item 3} & \text{3 USD} & \text{Small} & \text{tmw} \\ \end {array} $$
	* $$ \begin{array}{c|} \text{Header} & \text{Price} & \text{Size} & \text{When} \\ \hline \text{Item 1} & \text{2 usd} & \text{big} & \text{now} \\ \hdashline \text{Item 3} & \text{3 USD} & \text{Small} & \text{tmw} \\ \end {array} $$
	* #table
		* Header
			* Price
			* Size
			* When
		* Item 1
			* 2 usd
			* big
			* now
		* Item 3
			* 3 USD
			* Small
			* tmw
		* Missing values

* 00: Valid dates (automatic)
	* !(2022-01-01 =>  !(2022-01-01
* 05: handle !today and !now (and equivalent with ? for inlining), ?now and ?today
* 07: day of the week name:
	* transform ?XXXX and !XXXX to a number of days offsetto reach that days, ex 
	* assuming that XXXX is the beginning of tha name of a day of the week
	* Examples
		* !(2023-03-20) => Next Monday
		* !(2023-03-20 | 13d) => next Monday Repeat every 13 day
		* !(2023-03-20 | 1m) => next Monday Repeat every 1 month
		* !(2023-03-20 | ~1m) => next Monday Repeat every 1 month from completion
		* ?mon and ?lun 
* 08: case of 07 but without future date provided, only repetioin
	* Will create the event in the repetion time delay, and obviously repeating
	* Example: !r1w => in 1 repeating every week
	* !r in 1 day repeating every day
* 10: General date transofmration
	* Point int time part
		* ? inling, otherwise !
		* Once for exact date offset, twice for next date falling on that day
		* Can then be written as 10, 10d (default is d), 10w, 10m, 10y
		* Example:
			* ??1
			* !(2023-04-01)
			* ?1
			* !(2023-03-17)
	* Recurrence part
		* Start with r, only work with single ? or !
		* same offset as before: 10, 10d, 10w, 10m, 10y
		* then f, fc or c: from completion (not by default)
	* Example
		* !(2023-03-20) => next 20 of month (this month or following one)
		* !(2023-04-10 | ~1m) => next 10 of month (this month or following one), then repeat every month from completion
		* !(2023-03-17) in 1 day
		* !(2023-04-15) in 1 month
* 50: Phone number transformation, not detailled

* Other note: ,,digit is removed and turned to the corresponding color with the Prioritise pluging

* Other notes: the date sw\apper with weekday match a !, @ , or # followed by week or weekX (example !weekday)

* #now 
* #today


* Testing:
	* No repeition
		* No time
			* Single date
			* Duration
		* Time
			* Single date
			* Duration
			* Test repetition
