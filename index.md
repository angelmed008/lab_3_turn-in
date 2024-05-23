# Failure-Inducing Input
## JUnit test for failure-inducing input:
 import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
  @Test
  public void testReverseInPlaceFailureInducing() {
    int[] input = {1, 2, 3, 4};
    ArrayExamples.reverseInPlace(input);
    // Expected output: {4, 3, 2, 1}
    // The buggy implementation will produce an incorrect output
    assertArrayEquals(new int[]{4, 3, 2, 1}, input);
  }
}
# Failure-Inducing Input
## JUnit test for the non-failure-inducing input:

import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
  @Test
  public void testReverseInPlaceNonFailureInducing() {
    int[] input = {3};
    ArrayExamples.reverseInPlace(input);
    // Expected output: {3}
    // The buggy implementation will produce: {3}
    assertArrayEquals(new int[]{3}, input);
  }
}
# Symptom
Below is a screenshot of the output of running the two tests. One test should pass (the non-failure-inducing input), and the other test should fail (the failure-inducing input).

The Bug
Before code change:
![Image](12.jpg)
