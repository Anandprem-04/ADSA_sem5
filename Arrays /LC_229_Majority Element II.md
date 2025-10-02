## LC_SUBMISSION
https://leetcode.com/problems/majority-element-ii/submissions/1754911685/
## APPROACH

## CODE
    public List<Integer> majorityElement(int[] nums) {

        int e1 = Integer.MIN_VALUE;
        int e2 = Integer.MIN_VALUE;
        int c1 = 0 , c2 = 0;
        List<Integer> arr = new ArrayList<>();
        for(int a : nums){
            if(c1 == 0 && a != e2){
                c1++;
                e1 = a;
            }else if(c2 == 0 && a != e1) {
                c2++;
                e2 = a;
            }else if (e1  == a) {c1++;}
            else if (e2 == a) {c2++;}
            else {c1--; c2--;}
        }
        c1 = 0;
        c2 = 0;
        for (int a : nums) {
            if (a == e1) c1++;
            else if (a == e2) c2++;
        }
        int freq  = (nums.length)/3;
        if (c1>freq) arr.add(e1);
        if(c2>freq) arr.add(e2);
        return arr;
    }
