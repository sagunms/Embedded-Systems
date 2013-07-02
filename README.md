# Embedded Systems #

## Prime Number Verifier ##

System Generator FPGA design to determine if a positive integer is a prime number. This is based on the following Matlab implementation of Prime Number Verifier.

```
#!matlab

function output = is_prime(n)
switch n
	case {0, 1}
		output = false;
	case {2}
		output = true;
	otherwise
		output = true;
		for i = 2:(n-1)
			remainder = rem(n, i);
			if (remainder == 0)
			output = false;
			break;
		end
	end
end
```

## Square Root Finder ##

System Generator FPGA design to calculate the square root of an integer. This is based on the following Matlab implementation of Square Root Finder by Newton's method.

```
#!matlab

function y = square_root(x)
y0 = floor(x/2) + 1;
while (true)
	y_div = floor(x/y0);
	y_next = floor((y0 + y_div)/2);
	fprintf('Itr: y0 = %f, y_next = %f\n', y0, y_next);
	if (y_next >= y0)
		break;
	else
		y0 = y_next;
	end
end
y = y_next;
fprintf('Result: y = %f\n', y);
```

## Software Used ##

* Xilinx ISE Design Suite - System Edition Version 14
* MATLAB R2012b
* Windows 7 Ultimate x86
