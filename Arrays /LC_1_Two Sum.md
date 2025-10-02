## LC_SUBMISSION
https://leetcode.com/problems/two-sum/submissions/1765295032/
## APPRAOCH

## CODE
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> mpp = new HashMap<>();
        for(int i=0; i<nums.length; i++){
            int tar = target-nums[i];
            if(mpp.containsKey(tar)){
                int[] arr = {mpp.get(tar),i};
                return arr;
            }
            mpp.put(nums[i],i);

        }
        return null;
    }
