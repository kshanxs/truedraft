# Example: Coding-First Assignment (CS/Data Science)

**User Prompt:**
> "Solve this Python assignment: Given an array of integers, return the length of the longest subarray with sum exactly K. Explain your approach and complexity."

---

## Mode Detected

`coding-first` using the CS/data-science discipline profile.

---

## Output

### Problem Restatement

Given an integer array and target value `K`, find the maximum length of a contiguous subarray whose sum is exactly `K`.

### Approach

A prefix-sum map is used to track the first index where each cumulative sum appears.

If the current prefix sum is `current_sum`, then a previous prefix sum of `current_sum - K` indicates a subarray ending at the current index with total sum `K`. Storing only the first index for each prefix sum guarantees the longest distance when a match appears later.

This is preferred over nested loops because it reduces time from quadratic to linear while keeping implementation concise.

### Implementation

```python
def longest_subarray_sum_k(values: list[int], target_sum: int) -> int:
    first_seen_index: dict[int, int] = {0: -1}
    running_sum = 0
    best_length = 0

    for index, number in enumerate(values):
        running_sum += number

        needed_prefix = running_sum - target_sum
        if needed_prefix in first_seen_index:
            candidate_length = index - first_seen_index[needed_prefix]
            if candidate_length > best_length:
                best_length = candidate_length

        # Keep the earliest index to maximize future subarray lengths.
        if running_sum not in first_seen_index:
            first_seen_index[running_sum] = index

    return best_length
```

### Complexity Analysis

- Time Complexity: O(n)
- Space Complexity: O(n)

### Testing Notes

Suggested checks:

- all positive values
- mixture of positive and negative values
- no valid subarray
- multiple valid subarrays where the longest is not first

### Possible Improvements

- Return start/end indices along with length for debugging or report appendices.
- Add property-based tests to stress random inputs.

---

## Integrity Notes

- If the assignment asks for benchmark comparisons, keep placeholders unless benchmark context is supplied: `[CITE: benchmark source]`
- If this code is inserted into a report, include a short rationale for prefix sums and mention assumptions about integer ranges.
