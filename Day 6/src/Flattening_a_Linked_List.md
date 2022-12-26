<h1> 	Flattening of a LinkedList</h1> <br>
  
  <pre>
  
  class GfG
{
    Node flatten(Node root)
    {
	// Your code here
	    
	    Node n=root;
	    while(root.next!=null){
	        merge(root,root.next);
	       
	        root.next=root.next.next;
	    }
	    
	    return root;
    }
    
    void merge(Node l,Node r){

        while(l.bottom!=null && r!=null){
            if(l.bottom.data>r.data){
                Node n=new Node(r.data);
                n.bottom=l.bottom;
                l.bottom=n;
                r=r.bottom;
                l=l.bottom;
            }else{
                l=l.bottom;
            }
            
        }
        
        while(r!=null){
             Node n=new Node(r.data);
                n.bottom=l.bottom;
                l.bottom=n;
                r=r.bottom;
                l=l.bottom;
        }
        
    }
    
}
  </pre>
