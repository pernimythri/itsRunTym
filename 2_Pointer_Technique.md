 26. Remove Duplicates from Sorted Array

class Solution {
    public int removeDuplicates(int[] nums) {
        int j=0;
        for(int i=1;i<nums.length;i++)
        {
            if(nums[i]!=nums[j])
            {
                j++;
            nums[j]=nums[i];
            }
        }
        return j+1;
    }
}

------------------------------------------------
 167. Two Sum II - Input Array Is Sorted

class Solution {
    public int[] twoSum(int[] numbers, int target) {
        int  left=0,right=numbers.length-1;
        while(left<right)
        {
            if((numbers[left]+numbers[right])==target)
            break;
            else if((numbers[left]+numbers[right])>target)
            right--;
            else
            left++;
        }
        return new int[] {left+1,right+1};
    }
}

-------------------------------------------------
 283. Move Zeroes

class Solution {
    public void moveZeroes(int[] nums) {
        int j=0;
        for(int i=0;i<nums.length;i++)
        {
            if(nums[i]!=0)
            {
                nums[j]=nums[i];
                j++;
            }
        }
        for(int zero=j;zero<nums.length;zero++)
        {
            nums[zero]=0;
        }
    }
}

---------------------------------------------------
 344. Reverse String

class Solution {
    public void reverseString(char[] s) {
        int left=0,right=s.length-1;
        while(left<right)
        {
            char temp=s[left];
            s[left]=s[right];
            s[right]=temp;
            left++;
            right--;
        }
    }
}

---------------------------------------------------
 11. Container With Most Water

class Solution {
    public int maxArea(int[] height) {
        int left=0,right=height.length-1;
        int maxArea=0;
        while(left<right)
        {
            int min=Math.min(height[left],height[right]);
            int distance=right-left;
            int area=min*distance;
             maxArea=Math.max(area,maxArea);
            if(height[left]<height[right])
            left++;
            else
            right--;
        }
        return maxArea;
    }
}

---------------------------------------------------
125. Valid Palindrome

class Solution {
    public boolean isPalindrome(String s) {
        s=s.toLowerCase();
        int left=0,right=s.length()-1;
        while(left<right)
        {
            while(left<right && (!Character.isLetterOrDigit(s.charAt(left))))
            left++;
            while(left<right && (!Character.isLetterOrDigit(s.charAt(right))))
            right--;

            if(s.charAt(left)!=s.charAt(right))
            return false;
            left++;
            right--;
        }
        return true;
    }
} 
--------------------------------------------------------
977. Squares of a Sorted Array

978. 
