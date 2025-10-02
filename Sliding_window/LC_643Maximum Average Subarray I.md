## LC_SUBMISSION
https://leetcode.com/problems/maximum-average-subarray-i/submissions/1758025696/
## APPROACH

## CODE
    public double findMaxAverage(int[] nums, int k) {
        int sum = 0;
        for(int i=0; i<k; i++){
            sum += nums[i]; 
        }
        int max = sum ;

        for(int j = 0; j<nums.length-k; j++){
            sum = sum - nums[j]+nums[j+k];
            if  (sum > max ) max = sum;
        }
        return (double) max/k;
    }
