<h1> Largest subarray with 0 sum</h1><br>

<pre>

class GfG
{
    int maxLen(int arr[], int n)
    {
        Map<Integer,Integer> map=new HashMap<>();
        int max=0;
        int sum=0;
        for(int i=0;i<arr.length;i++){
            sum+=arr[i];
            
            if(sum == 0) {
                max = i + 1; 
            }

            if(!map.containsKey(sum)){
                map.put(sum,i);
            }else{
                max=Math.max(max,i-map.get(sum));
            }
        }
        return max;
    }
}


</pre>
