# Linkedlist
public class LinkedList {
    public static class Node {
        int data;
        Node next;
        public Node(int data) {
            this.data  = data;
            this.next = null;
        }
    }
    public static Node head;
    public static Node tail;
    public static int size;
    public void addFirst(int data) {
        Node newNode = new Node(data);
        size++;
        if(head == null) {
            head = tail = newNode;
            return;
        }
        newNode.next = head; // link
        head = newNode;
    }
    public void addLast(int data) {
        Node newNode = new Node(data);
        size++;
        if(head == null) {
            head = tail = newNode;
            return;
        }
        tail.next = newNode; // linl
        tail = newNode;
    }
    public void print() {
        if(head == null) {
            System.out.println("LL IS EMPTY");
            return;
        }
        Node temp = head;
        while(temp != null) {
            System.out.print(temp.data + " -> ");
            temp = temp.next;
        }
        System.out.println("null");

    }
    public void add(int idx, int data) {
        if(idx == 0) {
            addFirst(data);
            return;
        }
        Node newNode = new Node(data);
        size++;
        Node temp = head;
        int i = 0;
        while(i<idx-1) {
            temp = temp.next;
            i++;
        }
        // insert i = idx-1; temp -> prev
        newNode.next = temp.next;
        temp.next = newNode;

    }
    public int removefirst() {
        if(size == 0) {
            System.out.println("LL is empty");
            return Integer.MIN_VALUE;
        } else if(size == 1) {
            int val = head.data;
            head = tail = null;
            return val;
        }
        int val = head.data;
        head = head.next;
        return val;
    }
    public static void main(String[] args) {
        LinkedList ll = new LinkedList();
      //  ll.print();
        ll.addFirst(2);
      //  ll.print();
        ll.addFirst(1);
       // ll.print();
       ll.adpublicdLast(4);
       // ll.print();
        ll.addLast(5);
        ll.add(2, 3);
       ll.print(); // 1->2->3->4->5->null
       // System.out.println(ll.size);
       ll.removefirst();
       ll.print();
    }
}
