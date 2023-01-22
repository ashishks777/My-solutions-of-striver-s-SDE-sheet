<h1> Fractional Knapsack Problem</h1><br>

<pre>

public class  pw implements Comparator<Item>{
    @Override
    public int compare(Item a,Item b){
        double res= (double)b.value/(double)b.weight-(double)a.value/(double)a.weight;
        
        if(res &gt 0){
            return +1;
        }
        if(res &lt 0){
            return -1;
        }
        return 0;
    }
}

class Solution
{
    //Function to get the maximum total value in the knapsack.
    
    double fractionalKnapsack(int W, Item arr[], int n) 
    {
        // Your code here
        Arrays.sort(arr,new pw());
        
        int sum=0;
        double val=0;
        
        for(int i=0;i &lt arr.length;++i){
           
            if((sum+arr[i].weight) &gt W){
                val+=((double)arr[i].value/(double)arr[i].weight)*(double)(W-sum);
                return val;
            }else{
                sum+=arr[i].weight;
                val+=arr[i].value;
            }
        }
        return val;
    }
}


</pre>
