#include <iostream>
using namespace std;
class library
{
public:
    string author, title;
    double isbn,searchisbn;
    void get();
    void display();
    bool search(double);
};
void library::get()
{
    cout << "enter the isbn of the book: ";
    cin >> isbn;
    cout << "enter the author of the book: ";
    cin >> author;
    cout << "enter the title of the book: ";
    cin >> title;
}

bool library::search(double x)
{
    return x == isbn;
    
}

void library ::display()
{
    cout << "isbn : " << isbn << endl;
    cout << "title : " << title << endl;
    cout << "author: " << author << endl;
}

int main()
{
    int number, size;
    // library obj;
    cout << "enter the number of books you want to enter the details: ";
    cin >> size;
    library obj1[size];
    for (int i = 0; i < size; i++)
    {
        obj1[i].get();
    }

    cout << "enter the isbn of book you want to search: ";
    cin >> number;
    bool found = false;
    for (int i = 0; i < size; i++)
    {
        if (obj1[i].search(number))
        {
            cout << "book not found!";
            obj1[i].display();
            found = true;
            break;
        }
    }
        if(!found)
        cout<<"book found!";
}
