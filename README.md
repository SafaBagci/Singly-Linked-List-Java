# Singly-Linked-List-Java




public class SLLNode {

	public int data;
	public SLLNode next;
  
}






public class SimpleLinkList {
	private SLLNode head;
	
	public SimpleLinkList() {
		head = null;
	}
	
	public void addLast(int data) {
		//create new node
		SLLNode newnode = new SLLNode();
		newnode.data = data;
		newnode.next = null;
		
		if (head == null) head = newnode; //it fits first place because list is empty
		else {
			//i want to go last node 
			SLLNode p=head;
			while(p.next != null) p=p.next;
			p.next = newnode;
		}
	}
	public void addFirst(int data) {
		//create a new node
		SLLNode newnode = new SLLNode();
		newnode.data = data;
		newnode.next = head;
		head=newnode;
	}
	public void printIt() {
		SLLNode p=head;
		while (p!=null) {
			System.out.print(p.data + " -> ");
			p = p.next;
		}
		System.out.println("NULL");
	}
	public SLLNode find(int data){	
		SLLNode p = head;
		while (p!=null){
			if(p.data == data) break;
			p = p.next;
		}
		return p;
	}
	public void deleteIt(int data) {
		SLLNode p=head, q=null;   //p:this one  q:previous one
		while (p!=null && p.data != data) {
			q = p;
			p = p.next;
		}
		else if (q==null) head = p.next; //first factor
		else q.next = p.next;
	}
}
