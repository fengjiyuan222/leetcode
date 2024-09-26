给定一个整数数组 nums 和一个整数目标值 target
请你在该数组中找出和为目标值target的那两个整数
并返回它们的数组下标。

 class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) 
    {
        unordered_map<int, int> hashtable;
        for (int i = 0; i < nums.size(); ++i) 
        {
            auto it = hashtable.find(target - nums[i]);
            if (it != hashtable.end()) 
            {
                return {it->second, i};
            }
            hashtable[nums[i]] = i;
        }
        return {};
    }
};
