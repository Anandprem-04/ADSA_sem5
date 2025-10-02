## LC_SUBMISSION
https://leetcode.com/problems/maximum-subarray/submissions/1754209681/
## APPROACH

## CODE
    public int maxSubArray(int[] nums) {
        int max = Integer.MIN_VALUE;
        int sum = 0;
        for(int c : nums){
            sum += c;
             if (sum > max) max = sum;
            if (sum<0) sum = 0;
           
        }
        return max;
    }
