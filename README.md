# CVSS

This Python package contains CVSS v2 and v3 computation utilities and interactive calculator 
compatible with both Python 2 and Python 3.

It is tested on Python 2.7 and 3.4, but there is no magic or dependencies, so it should run or many
Python versions.

## Installation

    # pip install cvss

## Usage

### Library

	from cvss import CVSS2, CVSS3
	
	
	vector = 'AV:L/AC:L/Au:M/C:N/I:P/A:C/E:U/RL:W/RC:ND/CDP:L/TD:H/CR:ND/IR:ND/AR:M'
	c = CVSS2(vector)
	print(vector)
	print(c.clean_vector())
	print(c.scores())
	
	print()
	
	vector = 'S:C/C:H/I:H/A:N/AV:P/AC:H/PR:H/UI:R/E:H/RL:O/RC:R/CR:H/IR:X/AR:X/MAC:H/MPR:X/MUI:X/MC:L/MA:X'
	c = CVSS3(vector)
	print(vector)
	print(c.clean_vector())
	print(c.scores())
	print(c.severities())

Sample output:

	AV:L/AC:L/Au:M/C:N/I:P/A:C/E:U/RL:W/RC:ND/CDP:L/TD:H/CR:ND/IR:ND/AR:M
	AV:L/AC:L/Au:M/C:N/I:P/A:C/E:U/RL:W/CDP:L/TD:H/AR:M
	(5.0, 4.0, 4.6)
	
	S:C/C:H/I:H/A:N/AV:P/AC:H/PR:H/UI:R/E:H/RL:O/RC:R/CR:H/IR:X/AR:X/MAC:H/MPR:X/MUI:X/MC:L/MA:X
	AV:P/AC:H/PR:H/UI:R/S:C/C:H/I:H/A:N/E:H/RL:O/RC:R/CR:H/MAC:H/MC:L
	(6.5, 6.0, 5.3)
	('Medium', 'Medium', 'Medium')
	

### Interactive calculator

For interactive calculator run the following:

    $ cvss_calculator.py
    
For help on the calculator options run:

    $ cvss_calculator.py --help

## Testing

For extensive testing, the test vectors were generated using official JavaScript generators and 
[`cvsslib`](https://github.com/ctxis/cvsslib). 
 