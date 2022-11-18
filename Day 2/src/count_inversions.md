<h1> Inversion of Array (Pre-req: Merge Sort)</h1> 
<br>

<pre>
class Solution
{static int count=0;
    // arr[]: Input Array
    // N : Size of the Array arr[]
    //Function to count inversions in the array.
    static long inversionCount(long arr[], long N)
    {
        // Your Code Here
     
       return  mergeSort(arr,0,(int)N-1);
        
    }
    
    public static long merge(long arr[],int lo,int mid,int hi){
        int i=lo,j=mid+1,k=0;
        long count=0;
        long [] merged=new long[hi-lo+1];
        while(i<=mid && j<=hi){
            if(arr[i]<=arr[j]){
                merged[k++]=arr[i++];
                
            }else{
                merged[k++]=arr[j++];
                count+=mid-i+1;
            }
        }
        
        while(i<=mid){
                merged[k++]=arr[i++];
        }
        while(j<=hi){
             merged[k++]=arr[j++];
        }
        
        for(i=0;i&ltmerged.length;i++){
            arr[lo++]=merged[i];
        }
        return count;
    }
    
    
    public static long mergeSort(long arr[],int lo,int hi){
        if(lo<hi){
            int mid=(lo+hi)/2;
          return  mergeSort(arr,lo,mid)+ mergeSort(arr,mid+1,hi)+merge(arr,lo,mid,hi);
        }
        return 0;
    }
    
}
</pre>
