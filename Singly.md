```` java[]
# SINGLY LINKED LIST

import java.util.*;
class Node{         //Creating a class
    int data;
    Node next;
    
    Node(int data){         //Creating a Constructor
        this.data=data;     
        this.next=null;
    }
}
class LinkedList{           //Creating an another class for all the methods
    Node head,tail;
    public void insert(int data){
        Node newNode=new Node(data);
        if(head==null){
            head=newNode;
            tail=newNode;
        }
        else{
            tail.next=newNode;
            tail=newNode;
        }
    }
     public void insertAtBeginning(int data){       //Creating a method for inserting at Beginning 
        Node newNode=new Node(data);
        newNode.next=head;
        head=newNode;
    }
    public void insertAtEnd(int data){              //Creating a method for inserting at End
        Node newNode=new Node(data);
        Node temp=head;                             //Pointing temp to head
        while(temp.next!=null){
            temp=temp.next;
        }
        temp.next=newNode;
    }
    public void insertAtindex(int pos,int data){    //Creating a method for inserting at a specific index
        Node newNode=new Node(data);
        Node temp=head;
        int count=1;
        while(count<pos-1 && temp.next!=null){
            temp=temp.next;
            count++;
        }
        newNode.next=temp.next;
        temp.next=newNode;
    }
    public void deleteAtBeginning(){                //Creating a method for deleting at Beginning
        if(head!=null){
            head=head.next;
        }
    }
    public void deleteAtEnd(){                      //Creating a method for deleting at End
        Node temp=head;
        while(temp.next.next!=null){
            temp=temp.next;
        }
        temp.next=null;
    }
    public void deleteAtindex(int pos){             //Creating a method for deleting at specific index
        Node temp=head;
        for(int i=0;i<pos-1;i++){
            temp=temp.next;
        }
        head.next=temp.next;
    }
    public void display(){                          //Creating a method for displaying 
        Node temp=head;
        while(temp!=null){
            System.out.println(temp.data);
            temp=temp.next;
        }
    }
}
public class Main
{
    public static void main(String[] args){
        LinkedList link=new LinkedList();           //Creating an object for the class LinkedList
        link.insert(100);
        link.insert(200);
        link.insert(400);
        link.insertAtBeginning(0);
        link.insertAtEnd(500);
        link.insertAtindex(4,300);
        link.deleteAtBeginning();
        link.deleteAtEnd();
        //link.deleteAtindex(2);
        link.display();
    }
}
````
```` java[]
# Output
100
200
300
400
````
