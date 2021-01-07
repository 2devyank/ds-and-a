# Hashing

### Largest Subarray with Sum Zero Java

```java
import java.util.*;
import java.lang.*;
import java.io.*;

class Solution
{
    public static void main (String[] args) 
    {
        int arr[] = new int[]{5, 3, 9, -4, -6, 7, -1};
        int n = arr.length;
        
        System.out.println(ZeroSumSubarray(arr, n));
        
    }
    
    static int ZeroSumSubarray(int arr[], int n)
    {
        Set<Integer> us = new HashSet<Integer>();
        int prefix_sum = 0;
        us.add(0);
        for(int i = 0; i < n; i++)
        {
            prefix_sum += arr[i];
            if(us.contains(prefix_sum) == true)
              return 1;
              
            us.add(prefix_sum);
        }
        
        return 0;
    }
}

```

### Largest Sub Array With Sum X

```java
import java.util.*;
import java.lang.*;
import java.io.*;

class Solution
{
    public static void main (String[] args) 
    {
        int arr[] = new int[]{8, 3, -7, -4, 1};
        int n = arr.length;
        int sum = -8;
        
        System.out.println(largestSubarrayWithSumX(arr, n, sum));
        
    }
    
    static int largestSubarrayWithSumX(int arr[], int n, int sum)
    {
        int prefix_sum = 0;
        HashSet<Integer> us = new HashSet<>();
        us.add(0);
        for(int i = 0; i < n; i++)
        {
            prefix_sum += arr[i];
            if(us.contains(prefix_sum - sum))
              return 1;
            us.add(prefix_sum);
        }
        return 0;
    }
}

```

### Largest Zero Sub Array

```java
import java.util.*;
import java.io.*;
import java.lang.*;

class Main
{
    public static void main (String[] args) {
        int arr[] = new int[]{1, 1, 1, 0, 1, 0, 1, 1, 1};
        int len = arr.length;
        
        System.out.println(largestZeroSubarray(arr, len));
    }
    
    static int largestZeroSubarray(int arr[], int n)
    {
        Map<Integer, Integer> hm = new HashMap<Integer, Integer>();
        int sum = 0, maxLen = 0;
        for(int i = 0; i < n; i++)
         arr[i] = (arr[i] == 0) ? -1 : 1;
         
        for(int i = 0; i < n; i++)
        {
            sum += arr[i];
            if (sum == 0)
             maxLen = i+1;
             
            if(hm.containsKey(sum + n) == true)
            {
                if(maxLen < i - hm.get(sum + n))
                 maxLen = i - hm.get(sum + n);
                
            }else hm.put(sum + n, i);
        }
        return maxLen;
    }
}
```

### Pair with sum x :

```java
import java.util.*;
import java.io.*;
import java.lang.*;

class Main
{
    public static void main (String[] args) {
        int arr[] = new int[]{3, 8, 4, 7, 6, 1};
        int len = arr.length;
        int x = 14;
        System.out.println(pairWithSumX(arr, len, x));
    }
    
    static int pairWithSumX(int arr[],int n, int X)
    {
        HashSet<Integer> us = new HashSet<>();
        for(int i = 0; i < n; i++)
        {
            if(us.contains(X - arr[i]))
              return 1;
              
            us.add(arr[i]);
        }
        return 0;
        
    }
}
```


