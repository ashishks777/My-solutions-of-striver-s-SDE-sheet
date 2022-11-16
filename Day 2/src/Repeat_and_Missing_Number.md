
<h1> Using Extra space </h1>
<pre>
import java.util.* ;
import java.io.*; 
import java.util.ArrayList;

public class Solution {

    public static int[] missingAndRepeating(ArrayList<Integer> arr, int n) {
        // Write your code here
     int count[]=new int [arr.size()+1];
        for(int i=0;i<arr.size();i++){
            count[arr.get(i)]++;
        }
        
        int ans[]=new int[2];
        for(int i=1;i<count.length;i++){
            if(count[i]==0){
                ans[0]=i;
            }else if(count[i]==2){
                ans[1]=i;
            }
        }
        return ans;
        
    }
}
</pre>
<br> <br>
<h1>Using XOR (without extra space) </h1>
<pre>
import java.util.* ;
import java.io.*; 
import java.util.ArrayList;

public class Solution {

    public static int[] missingAndRepeating(ArrayList<Integer> arr, int n) {
        // Write your code here
     int xor=0;
        for(int i=0;i<arr.size();i++){
            xor^=arr.get(i);
        }
        for(int i=1;i<=n;i++){
            xor^=i;
        }
        
        int set_bit_no=0;
        int num=xor;
        while((num&1)!=1){
            set_bit_no++;
           num= num>>1;
        }
        
        int bucket1=0;
        int bucket2=0;

        for(int i=0;i<arr.size();i++){
            if(((arr.get(i)>>set_bit_no) &1)==1){
               
                bucket1^=arr.get(i);
            }else{
                bucket2^=arr.get(i);
            }
        }
        
        for(int i=0;i<=n;i++){
            if(((i>>set_bit_no) &1)==1){
                bucket1^=i;
            }else{
                bucket2^=i;
            }
        }
        
        if(arr.contains(bucket1)){
           int ans[]={bucket2,bucket1};
        
        return ans; 
        }else{
            int ans[]={bucket1,bucket2};
        
        return ans;
        }
        
   
    }
}
</pre>
