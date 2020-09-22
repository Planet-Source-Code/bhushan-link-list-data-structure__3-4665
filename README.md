<div align="center">

## Link list data structure


</div>

### Description

This is the stack link list data structure it have the structure of stack it have the function of add, remove, print, and search.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Bhushan\-](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/bhushan.md)
**Level**          |Beginner
**User Rating**    |5.0 (30 globes from 6 users)
**Compatibility**  |C
**Category**       |[Coding Standards](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/coding-standards__3-32.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/bhushan-link-list-data-structure__3-4665/archive/master.zip)





### Source Code

```
#include <iostream.h>
struct node
{
int num;
node *next;
};
class number
{
public:
number();
~number();
int add(int num, int success);
int remove(int num, int success);
void print();
int search(int num, int success);
private:
node *head;
node *cur;
node *pre;
};
//constructor
number::number()
{
head=NULL;
cur=NULL;
pre=NULL;
}
//destructor
number::~number()
{
node *ptr;
while(head!=NULL) //delete all the numbers
{
ptr=head->next;
delete head;
head=ptr;
}
}
void main()
{
char answer;
int num;
int success=0;
number link;
cout << "This is the the linked list function" << endl;
cout << "\n \n";
for(int i=5; i>3; i++) //loop is for keep the program run untill set it false
{
cout << "Enter 'A' for add a number" << endl; //main menus
cout << "Enter 'R' for remove a number" << endl;
cout << "Enter 'P' for print all the number" << endl;
cout << "Enter 'S' for search a number" << endl;
cout << "Enter 'Q' for quit the program" << endl;
cout << "\n\n";
cout << "Enter your choice of A, R, P, S, or Q: ";
cin >> answer;
//if choice was A or a, asked the user to enter a number then call the add
//function, the function will return success or fail
if((answer=='A')||(answer=='a'))
{
cout << "Enter a number: ";
cin >> num;
success=link.add(num, success);
if(success==1)
cout << "Add success" << endl;
else
cout << "Add fail" << endl;
}
else if((answer=='R')||(answer=='r'))
{
success=link.remove(num, success);
if(success==1)
cout << "Remove success" << endl;
else
cout << "Remove fail" << endl;
}
else if((answer=='P')||(answer=='p'))
link.print();
else if((answer=='S')||(answer=='s'))
{
cout << "Enter a number: ";
cin >> num;
success=link.search(num, success);
if(success==1)
cout << "Search success" << endl;
else
cout << "Search fail" << endl;
}
//if the user enter a Q or q, set the for loop at the beginning to false and
//quit the program.
else if((answer=='Q')||(answer=='q'))
i=0;
//if any other input other then A R, P, S, or Q then print out an error message
else
cout << "Error, you choice must be A, R, P, S, or Q";
i--; //the integer i will never get any larger.
} //for loop
}// main
//this is the link list add function by stack. If the it was empty, make a new cell
//copy the number to the new cell, else current equal to head, head equal to new cell
//copy the number to the head-> new cell. and new cell ->next equal to current. this
//will connect the list together.
int number::add(int num, int success)
{
if(head==NULL)
{
head=new node;
head->num=num;
head->next=NULL;
success=1;
}
else
{
cur=head;
head=NULL;
head=new node;
head->num=num;
head->next=cur;
success=1;
}
return success;
}
//****remove at the head, this is stack, add at the head remove at the head.
int number::remove(int num, int success)
{
node *temp; //make a temp pointer
if(head!=NULL) //if the list is not empty
{
temp=head->next; //temp equal to head ->next
delete head; //delete head, remove the first data of the list
head=temp; //now the second data of the list become the first data of the list
return success=1; //return success
}
else
return success=0; //if the list empty return fail
return success;
}
//this function will print from the beginning of the list to the end of the list
void number::print()
{
//if the list was empty print out an error message
if(head==NULL)
{
cout << "There isn't any number" << endl;
return;
}
//else while not the end of the list, print out the number and go to the next one
else
{
cur=head;
while(cur!=NULL)
{
cout << "number: " << cur->num << endl;
cur=cur->next;
}
}
}
//the search function was search from the beginning of the head to the end of the
//head.
int number::search(int num, int success)
{
if(head==NULL) //if there isn't any data return 0
{
success=0;
return 0;
}
if(head->num == num) //if delete the first node
{
cout << num << " was found" << endl;
success=1;
return 1;
}
else //else delete any node other than the first node
{
cur=head;
cur=cur->next;
while(cur!=NULL) //search all the to the end of the list
{
if(cur->num ==num)
{
cout << num << " was found" << endl;
success=1;
return 1;
}
pre=cur;
cur=cur->next;
success=0;
}// while
} //else
return success;
}
```

