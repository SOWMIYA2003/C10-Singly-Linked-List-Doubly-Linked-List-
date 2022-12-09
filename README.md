# C10-Singly-Linked-List-Doubly-Linked-List-
## Singly-Linked-List
### TRAVERSAL
```
struct Node{
    float data; 
    struct Node *next;
}*head;
void display()
{
    struct Node *temp;
    temp = head;
    while(temp!=NULL)
    {
        printf("%.3f ",temp->data);
        temp = temp->next;
    }
}
```
### SEARCH 
```
struct Node{
    char data; 
    struct Node *next;
}*head;
void search(char data)
{
 struct Node *ptr;
 char item=data;
 int i=0,flag;
 ptr = head;
 if(ptr == NULL)
 {
     printf("\nEmpty List\n");
 }
 else{
     while(ptr!=NULL)
     {
         if(ptr->data == item)
         {
             printf("item %c found at location %d ",item,i+1);
             flag=0;
         }
         i++;
         ptr=ptr->next;
     }
     if(flag!=0)
     {
         printf("Item not found\n");
     }
 }
}
```
### DELETE
```
struct Node{
    char data; 
    struct Node *next;
}*head;
void delete()
{
    struct Node *ptr;
    if(head == NULL)
    {
        printf("List is empty\n");
    }
    else
    {
        ptr = head;
        head = ptr->next;
        free(ptr);
        printf("Node deleted from the begining ...\n");
    }
}
```
### INSERTION
```
struct Node{
    int data; 
    struct Node *next;
}*head;
void insert(int data)
{
    struct Node *n=(struct Node*)malloc(sizeof(struct Node));
    struct Node *temp;
    if(head==NULL)
    {
        head = n;
        head->data = data;
        n->next=NULL;
        return;
    }
    temp=head;
    while(temp->next!=NULL)
    {
        temp=temp->next;
    }
    n->data = data;
    n->next = NULL;
    temp->next= n;    
}
```
## Doubly-Linked-List
### TRAVERSAL
```
struct Node
{
    struct Node *prev;
    struct Node *next;
    float data;
}*head;
void display()
{
    struct Node *ptr;
    ptr = head;
    while(ptr != NULL)
    {
        printf("%.2f ",ptr->data);
        ptr=ptr->next;
    }
}
```
### SEARCH 
```
struct Node
{
    struct Node *prev;
    struct Node *next;
    float data;
}*head;
void search(float data)
{
    struct Node *ptr;
    float item=data;
    int i=0,flag;
    ptr = head;
    if(ptr == NULL)
    {
    printf("Empty List\n");
    }
    else{
        while (ptr!=NULL)
        {
            if(ptr->data == item)
            {
                printf("item %.2f found at location %d\n",item,i+1);
                flag=0;
            }
            i++;
            ptr = ptr -> next;
        }
        if(flag!=0)
        {
            printf("Item not found\n");
        }
    }
}
```
### DELETE
```
struct Node
{
    struct Node *prev;
    struct Node *next;
    int data;
}*head;
void delete()
{
    struct Node *ptr;
    if(head == NULL)
    {
        printf("UNDERFLOW\n");
    }
    else if(head->next == NULL)
    {
        head = NULL;
        free(head);
        printf("node deleted\n");
    }
    else
    {
        ptr = head;
        head = head -> next;
        head -> prev = NULL;
        free(ptr);
        printf("node deleted\n");
    }
}
```
### INSERTION
```
struct Node
{
    struct Node *prev;
    struct Node *next;
   char data;
}*head;
void insert(char data)
{
   struct Node *ptr,*temp;
   ptr = (struct Node *) malloc(sizeof(struct Node));
   if(ptr == NULL)
   {
       printf("OVERFLOW\n");
   }
   else
   {
        ptr->data=data;
       if(head == NULL)
       {
           ptr->next = NULL;
           ptr->prev = NULL;
           head = ptr;
       }
       else
       {
          temp = head;
          while(temp->next!=NULL)
          {
              temp = temp->next;
          }
          temp->next = ptr;
          ptr ->prev=temp;
          ptr->next = NULL;
          }
       }
    }
```
