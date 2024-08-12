#linked list
class Node {
    int data;
    Node Next;
}

public class LinkedList {
    Node head;

    public void insert(int data) {
        Node node = new Node();
        node.data = data;

        if (head == null) {
            head = node;
        } else {
            Node n = head;
            while (n.Next != null) {
                n = n.Next;
            }
            n.Next = node;
        }
    }

    public void insertAtStart(int data) {
        Node n = new Node();
        n.data = data;
        if (head == null) {
            head = n;
        } else {
            n.Next = head;
            head = n;
        }

    }

    public void insertAtPosition(int pos, int data) {
        Node newnode = new Node();
        newnode.data = data;
        newnode.Next = null;
        Node n = head;

        if (pos == 0) {
            insertAtStart(data);
        } else {

            for (int i = 0; i < pos - 1; i++) {
                n = n.Next;
            }
            newnode.Next = n.Next;
            n.Next = newnode;
        }
    }

    public void deleteAtstart() {
        Node n = head;
        if (n == null) {
            System.out.println("not possible");
        } else {
            head = head.Next;
        }
    }

    public void deleteAtEnd() {
        Node a = head;
        Node b = a.Next;
        while (b.Next != null) {
            a = b;
            b = b.Next;
        }
        a.Next = null;

    }

    public void deleteAt(int pos) {
        Node n = head;
        if (n == null) {
            System.out.println("not possible");
        } else {
            for (int i = 0; i < pos - 1; i++) {
                n = n.Next;
            }
            Node temp = n.Next;
            n.Next = temp.Next;

        }

    }

    public void display() throws NullPointerException {
        Node n = head;
        while (n != null) {
            System.out.println(n.data);
            n = n.Next;
        }
        System.out.println(n.data);
    }

    public static void main(String[] args) throws NullPointerException {
        LinkedList li = new LinkedList();

        li.insert(5);
        li.insert(6);
        li.insert(7);
        li.insert(8);

        li.insertAtPosition(3, 10);
        li.deleteAtstart();
        li.deleteAt(2);
        li.deleteAtEnd();
        li.display();
    }
}









#double linked list



class NODE {
    int data;
    NODE next;
    NODE prev;
}

public class doubleLinkedList {
    NODE head;

    public void insert(int data) {
        NODE newn = new NODE();
        newn.data = data;
        newn.next = null;
        newn.prev = null;
        if (head == null) {
            head = newn;
        } else {
            NODE n = head;
            while (n.next != null) {
                n = n.next;
            }
            n.next = newn;
            newn.prev = n;
        }
    }

    public void showfor() {
        NODE n = head;
        while (n.next != null) {
            System.out.println(n.data);
            n = n.next;
        }
        System.out.println(n.data);
    }

    public void showrev() {
        NODE n = head;
        while (n.next != null) {
            n = n.next;
        }

        while (n.prev != null) {
            System.out.println(n.data);
            n = n.prev;
        }
        System.out.println(n.data);
    }


    public static void main(String[] args) {
        doubleLinkedList dli = new doubleLinkedList();

        dli.insert(2);
        dli.insert(3);
        dli.insert(4);
        dli.insert(5);
        dli.insert(6);

        dli.showrev();

    }

}
