# Math & messages

* `rand_between`: bang for random numbers between `#1` and `#2`.
Reset range using inlets.

* `plus_minus`: sends `inlet 1 + inlet 2` out `outlet 2` and `inlet 1 - inlet 2` out `outlet 1`.
Recognizes creation arguments.

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

