# LEETCODE-3264-Priority_Queue
Let's dry run the provided `getFinalState` function to understand its behavior. This function performs the following steps:

1. Finds the index of the smallest number in the `nums` array.
2. Multiplies that number by the `multiplier`.
3. Repeats the above steps `k` times.
4. Returns the final state of the `nums` array.

### Example Dry Run
Input:
```java
nums = [3, 5, 2, 8];
k = 2;
multiplier = 3;
```

**Initialization:**
- `nums = [3, 5, 2, 8]`
- `k = 2`
- `multiplier = 3`
- Length of `nums`, `n = 4`

---

#### Iteration 1 (`j = 0`):
1. Initialize `idx = 0` (starting with the first element).
2. Loop through `nums` to find the smallest element:
   - Compare `nums[0] = 3` with `nums[idx] = 3` → No change, `idx = 0`.
   - Compare `nums[1] = 5` with `nums[idx] = 3` → No change, `idx = 0`.
   - Compare `nums[2] = 2` with `nums[idx] = 3` → Update `idx = 2` (smallest so far).
   - Compare `nums[3] = 8` with `nums[idx] = 2` → No change, `idx = 2`.
3. Multiply the smallest number `nums[idx]` by `multiplier`:
   - `nums[2] *= 3 → nums[2] = 2 * 3 = 6`.
4. Updated array after the first iteration:
   - `nums = [3, 5, 6, 8]`.

---

#### Iteration 2 (`j = 1`):
1. Initialize `idx = 0`.
2. Loop through `nums` to find the smallest element:
   - Compare `nums[0] = 3` with `nums[idx] = 3` → No change, `idx = 0`.
   - Compare `nums[1] = 5` with `nums[idx] = 3` → No change, `idx = 0`.
   - Compare `nums[2] = 6` with `nums[idx] = 3` → No change, `idx = 0`.
   - Compare `nums[3] = 8` with `nums[idx] = 3` → No change, `idx = 0`.
3. Multiply the smallest number `nums[idx]` by `multiplier`:
   - `nums[0] *= 3 → nums[0] = 3 * 3 = 9`.
4. Updated array after the second iteration:
   - `nums = [9, 5, 6, 8]`.

---

#### Final State:
After completing `k = 2` iterations, the final array is:
```java
nums = [9, 5, 6, 8];
```

### Observations:
1. The algorithm identifies the smallest number in each iteration and multiplies it by the given `multiplier`.
2. Each operation modifies the `nums` array in-place.
3. Time Complexity:  
   - Finding the smallest element takes \(O(n)\).
   - This is repeated \(k\) times.  
   - Total: \(O(k \cdot n)\).
