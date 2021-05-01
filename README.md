# TwoSum

class Solution {
    fun twoSum(nums: IntArray, target: Int): IntArray {
        
        val map = hashMapOf<Int,Int>()
        
        //this will cause cases like [3,3] to fail
        //nums.forEachIndexed({ i,e -> map.put(e,i)})
        
        var sum = 0
        
        // I put intArrayOf mistakenly,
        // it is: "IntArray"
        var res  = IntArray(2)
        
        nums.forEachIndexed({ i,e -> 

            if(map.containsKey(target-e)){
                res[0] = i
                res[1] = map.get(target-e)!!
            }
            
            //record what we have seen before
            map.put(e,i)
        })
        
        return res
    }
}
