# Remove Element(移除元素):
## 核心觀念:
### 1.數列是一個"連續"的類型相近的元素集合。
### 2.所謂移除，並不是刪除，而是對目標元素進行"覆蓋"。
### 3.在各種程式語言中，移除元素後，取其長度(len(nums))，確實會減小，但在實際空間上，其實陣列的整體空間大小不變。
# Code #1(Pointers_fast ans slow) //Python
    nums = [1, 2, 3, 4, 5]  /*初始數列*/
    target = 3 /*移除目標*/
    pointer_fast = 0 /*快指針先跑*/ /*用來找尋要刪除的數值*/ /*如果沒找到，則把當前數值給到慢指針上*/
    pointer_slow = 0 /*慢指針後跑*/
    size = len(nums)
    while(pointer_fast < size): /*在數列內移動*/
        if(nums[pointer_fast] != target):
            nums[pointer_slow] = nums[pointer_fast]
            pointer_slow += 1
        pointer_fast += 1

    return pointer_slow, nums


# Code #2(The Simple method) //Python
    nums = [1, 2, 3, 4, 5]  /*初始數列*/
    target = 3 /*移除目標*/
    counter = 0
    size = len(nums)
    while(counter < size): /*在數列內移動*/
        if(nums[counter] = target): /*找到目標值*/
            for(i in range(counter+1, size): /*覆蓋該元素，其後所有元素向左平移一格*/
                nums[i-1] = nums[i]
            counter -= 1 /*向左平移*/
            size -= 1 /*忽略被覆蓋元素*/
        counter += 1

    return counter, nums

# Code #3(Pointers) //Python
    nums = [1, 2, 3, 4, 5]  /*初始數列*/
    target = 3 /*移除目標*/
    size = len(nums)
    left_pointer, right_pointer = 0, size-1
    while left <= right:
        while left_pointer <= right_pointer and nums[left_pointer] != target:
            left += 1
        while left_pointer <= right_pointer and nums[right_pointer] != target:
            right -= 1
        if left < right:
            nums[left_pointer] = nums[right_pointer]
            left += 1
            right -= 1
    return left_pointer, nums

# LeetCode:<https://leetcode.com/problems/remove-element/description/>
# My_LeetCode_Solution:<https://github.com/littleyu0820/LeetCode_Exercises/blob/main/Exercise/Remove_Element.py>
    
    
