## LC_SUBMISSION
https://leetcode.com/problems/grumpy-bookstore-owner/submissions/1773719832/
## APPROACH

## CODE
    public int maxSatisfied(int[] customers, int[] grumpy, int minutes) {
        int max = 0;
        int s  = 0;
        for(int i=0; i<=customers.length-minutes; i++){
            int sum =0;
            for(int j = i; j<i+minutes; j++){    
                if(grumpy[j]== 1) sum += customers[j];
            }
            if (sum > max) max = sum ;
        }
        int ts = 0;
        for (int i=0; i<customers.length; i++){
            if (grumpy[i]==0) ts+=customers[i];
        }
        return ts + max;
    }
