# Math & messages

* `rand_between`: bang for random numbers between `#1` and `#2`.
Reset range using inlets.

* `plus_minus`: function depends on creation arguments `#1 #2 #3`
	* if `#3 == 'sum'` or none, sends `inlet 1 + inlet 2` out `outlet 2` and `inlet 1 - inlet 2` out `outlet 1`.
	* if `#3 == 'product'`, sends `inlet 1 * inlet 2` out `outlet 2` and `inlet 1 - inlet 2` out `outlet 1`
	* Recognizes creation arguments `#1 #2` as defaults for inlets 1 and 2

* `random_list_element`: send a list to right inlet, bang left inlet for a random element

* `send_to`: given a list `meh psh`, sends message `psh` to `[receive #0-meh]`

* `metro_between`: a `metro` that resets its own interval.
If `#3 == 'random'` then interval is uniform random between `#1` and `#2`.
If `#3 == `drunk` then interval is set by drunken walk between `0` and `#1` with a maximum step size of `#2`.

# Audio

## Granular synthesis

* `groove_grain~`: voice for a single grain.
Intended for `poly~`.
	* Creation arguments:
		* `#1`: playback buffer name
		* `#2`: window buffer name
	* `inlet 1` messages:
		* `float`: start position (ms), triggers grain
		* `inlet 2` messages:
			* `length_min` (ms)
			* `length_max`
			* `amp_min` (0 - 1 scale)
			* `amp_max`
			* `pan_min` (-50 - 50 scale)
			* `pan_max`

* `grain_banger~`: 'spitter' for `groove_grain~`
