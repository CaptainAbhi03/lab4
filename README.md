#include <stdio.h>
#include <stdlib.h>
//Represent a node of singly linked list
struct node{
    int data;
    struct node *next;
};

//Represent the head and tail of the singly linked list
struct node *head, *tail = NULL;

//addNode() will add a new node to the list
void addNode(int data) {
    //Create a new node
    struct node *newNode = (struct node*)malloc(sizeof(struct node));
    newNode->data = data;
    newNode->next = NULL;

    //Checks if the list is empty
    if(head == NULL) {
        //If list is empty, both head and tail will point to new node
        head = newNode;
        tail = newNode;
    }
    else {
        //newNode will be added after tail such that tail's next will point to newNode
        tail->next = newNode;
        //newNode will become new tail of the list
        tail = newNode;
    }
}

//display() will display all the nodes present in the list
void display() {
    //Node current will point to head
    struct node *current = head;

    if(head == NULL) {
        printf("List is empty\n");
        return;
    }
    printf("Nodes of singly linked list: \n");
    while(current != NULL) {
        //Prints each node by incrementing pointer
        printf("%d ", current->data);
        current = current->next;
    }
    printf("\n");
}

int main()
{
    //Add nodes to the list
    int n1,n2,n3;
    printf("there are three node \n enter data for 1st node");
    scanf("%d",&n1);
    printf("enter data for 2nd  node");
    scanf("%d",&n2);
    printf("enter data for 3rd node");
     scanf("%d",&n3);


    addNode(n1);
    addNode(n2);
    addNode(n3);


    //Displays the nodes present in the list
    display();

    return 0;
}
