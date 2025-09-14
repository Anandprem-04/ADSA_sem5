## LC_209 (Minimum Size Subarray Sum)
https://leetcode.com/submissions/detail/1770048551/
## APPROACH 
Iterate J pointer till the end of array , Calculate Sum of everywindow till it gets greater than Target.

While(sum >= target )
 - If size < min , assign min = size ie (j-i+1);
 - Reduce the window size by increasing I pointer and subtract the element from sum .
   
return min if it gets changed else return 0 .
## CODE
    public int minSubArrayLen(int target, int[] nums) {
      int i = 0,j=0 , min= Integer.MAX_VALUE ;
      int sum = 0;
      while(j<nums.length){
        sum += nums[j];
        while(sum>=target) {
            int size = j-i+1;
            if(min > size) min = size; 
            sum -= nums[i];
            i++; 
        }
        j++;
      }
       return min==Integer.MAX_VALUE ? 0:min;
    }
