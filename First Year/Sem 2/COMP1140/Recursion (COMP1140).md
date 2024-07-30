>[!example]
>Implementing binary search for the root of a continuous and monotone function.

```java
public class EqSolve {
	static double solve(double lower, double upper) {
		double mid = (lower + upper) / 2;
		double val = mid * mid - 2; // f(x) = x^2 - 2
		// Base case
		if (Math.abs(val - 0) < 0.01f) {
			return mid;
		}
		// Recuse otherwise
		else if (val < 0) {
			return solve(mid, upper);
		}
		else {
			return solve(lower, mid);
		}
	}

	public static void main(String[] args) {
		System.out.println(
			"x_0 = ~%f.%n",
			solve(-5.0f, 5.0f)
		);
	}
}
```

