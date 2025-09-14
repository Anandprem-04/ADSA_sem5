## LC_1004 (Max Consecutive Ones III)
https://leetcode.com/submissions/detail/1770080855/
## APPROACH
- K is the number of Flips that can be done .
- Same as Approach for sliding window , Iterate J pointer till length of Array .
- Determine number of Zeros with a Count Variable . If count > K , remove the elements by increasing I pointer and if 0 exist on Ith position while removal , decrease the value of count before iteration .
- Calculate the size of window if Count =< K only .

- if size of the window is Greater than MAX value , assgin MAX = size , return max if value is altered else return 0 .

## CODE
    public int longestOnes(int[] nums, int k) {
        int i=0 , j=0 , cnt = 0 , max = Integer.MIN_VALUE;
        while(j<nums.length){
            if(nums[j]==0) cnt++;
            while(cnt>k){
                if(nums[i]==0) cnt--;
                i++;
            }
            int size = j-i+1;
            if(max<size) max = size;
            j++;
        }
        return max==Integer.MIN_VALUE?0:max;
    }
