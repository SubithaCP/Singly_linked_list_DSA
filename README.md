# Singly_linked_list_DSA
class Node{
    int data;
    Node next;
    Node(int data){
        this.data=data;
        this.next=null;
    }
}
class SinglyLinkedList{
    Node head;
    public void InsertAtBegin(int data){
        Node newNode=new Node(data);
        newNode.next=head;
        head=newNode;
    }
    public void InsertAtAnyPosition(int position, int data){
        if(position<=0){
            System.out.println("Invalid Position");
            return;
        }
        Node newNode=new Node(data);
        if(position==1){
            newNode.next=head;
            head=newNode;
            return;
        }
        Node temp=head;
        for(int i=0;i<position-1 && temp!=null;i++){
            temp=temp.next;
        }
        if(temp==null){
            System.out.println("Exceeds the position");
            return;
        }
        newNode.next=temp.next;
        temp.next=newNode;
    }
    public void deleteAtend(){
        if(head==null){
            System.out.println("List is empty");
            return;
        }
        Node temp=head;
        while(temp.next!=null && temp.next.next!=null){
            temp=temp.next;
        }
        temp.next=null;
    }
    public void display(){
        Node temp=head;
        while(temp!=null){
            System.out.println(temp.data+" ");
            temp=temp.next;
        }
        System.out.println();
    }
}
public class Main{
    public static void main(String[] args){
        SinglyLinkedList list=new SinglyLinkedList();
        list.InsertAtBegin(10);
        list.InsertAtBegin(20);
        list.InsertAtBegin(30);
        list.InsertAtBegin(40);
        list.InsertAtBegin(50);
        list.display();
        list.InsertAtAnyPosition(3,35);
        list.display();
        list.deleteAtend();
        list.display();
    }
}
OUTPUT:
50
40
30
20
10

50
40
30
35
20
10

50
40
30
35
20
