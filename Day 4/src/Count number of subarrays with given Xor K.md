<h1>	Count number of subarrays with given Xor K</h1>
<br>
<pre>
import java.util.* ;
import java.io.*; 
import java.util.* ;
import java.io.*; 
import java.util.ArrayList;

public class Solution {
	public static int subarraysXor(ArrayList<Integer> arr, int x) {
		// Write your code here.
        
        Map<Integer,Integer> map=new HashMap<>();
        
        int xor=0,count=0;
        for(int i=0;i<arr.size();i++){
            xor^=arr.get(i);
            if(xor==x)
                count++;
            if(map.containsKey(xor^x))
                count+=map.get(xor^x);
            
            map.put(xor,map.getOrDefault(xor,0)+1);
        }
        return count;
        
	}
}
</pre>
