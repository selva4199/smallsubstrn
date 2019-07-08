# smallsubstrn
NO_OF_CHARS = 256
def max_distinct_char(str1, n): 
    count1 = [0] * NO_OF_CHARS 
    for i in range(n): 
        count1[ord(str1[i])]+=1
    distinct = 0
    for i in range(NO_OF_CHARS): 
        if (count1[i] != 0): 
            distinct += 1    
    return distinct 
def smallesteSubstr_maxDistictChar(str1): 
    n = len(str1)
    max1= max_distinct_char(str1, n) 
    min1= n
    for i in range(n): 
        for j in range(n): 
            subs = str1[i:j] 
            subs_lenght = len(subs) 
            sub_distinct_char = max_distinct_char(subs,  
                                                  subs_lenght) 
            if (subs_lenght < min1 and 
                max1 == sub_distinct_char): 
                min1= subs_lenght 
    return min1
str1= "abcda"
l = smallesteSubstr_maxDistictChar(str1); 
print(l) 
