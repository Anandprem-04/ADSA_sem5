## LC_2210_Count_hill
https://leetcode.com/problems/count-hills-and-valleys-in-an-array/submissions/1754298785/

## APPROACH 
Distinct list leke , adjacent se compare karna h .

  
    public int countHillValley(int[] nums) {
        int h = 0;
        ArrayList<Integer> arr = new ArrayList<>();
        arr.add(nums[0]);
        for(int i=1; i<nums.length; i++){
            if (nums[i]==nums[i-1]) continue;
            arr.add(nums[i]);
        }
        for(int i=1; i<arr.size()-1; i++){
            if (arr.get(i-1) < arr.get(i) && arr.get(i) > arr.get(i+1)) h++;
            if (arr.get(i-1) > arr.get(i) && arr.get(i) < arr.get(i+1)) h++;
        }
        return h;
    }

