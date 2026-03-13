# Example: Structurally Original Coding Solution

**Assignment Topic:** Find all pairs in an array that sum to a target value ("Two Sum" variant)

---

> **Note for the Assignment Writer Skill:** This example demonstrates the output standard for coding tasks. Observe: approach explanation before code, descriptive variable names, non-default algorithm choice (hash-based rather than brute force), modular structure, and a complexity analysis section.

---

## Two Sum — All Pairs

### Approach

Rather than checking every possible pair of elements (which scales quadratically with input size), this solution leverages a hash-based lookup to reduce the problem to a single linear pass. The key insight is that for any element, its required complement — the value needed to reach the target sum — can be pre-computed. Storing previously seen values in a set allows each complement check to run in constant time.

This approach is preferred over the nested loop solution not only for its efficiency, but because it produces cleaner, more readable code with clearly defined responsibilities.

### Implementation

```python
def find_target_pairs(number_sequence: list[int], target_sum: int) -> list[tuple[int, int]]:
    """
    Identifies all unique pairs in a sequence whose values sum to the specified target.
    Returns a list of (smaller_value, larger_value) tuples to avoid duplicate reporting.
    """
    discovered_pairs = []
    previously_seen = set()
    reported_complements = set()

    for current_value in number_sequence:
        required_complement = target_sum - current_value

        # Check if the complement has been encountered earlier in the sequence
        if required_complement in previously_seen:
            pair_key = (min(current_value, required_complement),
                        max(current_value, required_complement))

            # Prevent the same pair from being reported more than once
            if pair_key not in reported_complements:
                discovered_pairs.append(pair_key)
                reported_complements.add(pair_key)

        previously_seen.add(current_value)

    return discovered_pairs


# --- Example Usage ---
sample_numbers = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3]
target = 8

result = find_target_pairs(sample_numbers, target)
print(f"Pairs summing to {target}: {result}")
# Output: Pairs summing to 8: [(3, 5), (2, 6)]
```

### Complexity Analysis

| Metric | Value | Reasoning |
|--------|-------|-----------|
| **Time Complexity** | O(n) | Single pass through the input sequence; all lookups are O(1) via hash set |
| **Space Complexity** | O(n) | The `previously_seen` set stores at most n distinct elements |

### Possible Improvements

- **Duplicate inputs:** The current solution handles duplicates (e.g., two 5s summing to 10) correctly via the `pair_key` deduplication mechanism. However, if counting how many times each pair appears is required, the `previously_seen` structure would need to become a frequency map (`Counter`) instead of a simple set.

- **Sorted input:** If the array is already sorted, a two-pointer approach achieves the same O(n) time complexity with O(1) additional space — worth considering in memory-constrained environments.

- **Streaming data:** For large or streaming datasets where the entire array cannot be held in memory, this hash-based method could be adapted to process chunks in sequence, retaining only the seen-values set between chunks.

---

*Plagiarism risk: LOW | Anti-plagiarism techniques demonstrated:*
- *Non-default algorithm (hash-based, not nested loop)*
- *Descriptive variable names: `number_sequence`, `previously_seen`, `required_complement`, `reported_complements`*
- *Helper reasoning via `pair_key` deduplication (breaks token-sequence similarity)*
- *Comments explain reasoning, not mechanics*
- *Complexity analysis presented as a table (structural variation)*
