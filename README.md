# students
#include <iostream>
#include <string>
#include <sstream>

using namespace std;
int main()
{
    setlocale(LC_ALL,"rus");
    struct student
    {
        string fio;
        int group;
        double score[5];
    };
    cout<<"Введите колличество учеников: ";
    int n;
    cin>>n;
    cout<<endl;
    student *st=new student[n];
    for (int i = 0; i!=n; i++) {
        cout<<"Введите фамилию: "<<endl;
        cin>>st[i].fio;
        cout<<"Введите номер группы: ";
        cin>>st[i].group;
        cout<<endl;
        cout<<"Успеваемость"<<endl<<endl;
        int j = 0;
        do
        {
            cout<<"Оценка: ";
            cin>>st[i].score[j];
            j++;
            
        }while(j!=5);
        double srball;
        srball=(st[i].score[0]+st[i].score[1]+st[i].score[2]+st[i].score[3]+st[i].score[4])/5;
        cout<<"Средний балл ученика: "<<srball<<endl;
        cout<<endl;
    }
    
        cout<<"Студенты со средним баллом >4: "<<endl;
        for (int i = 0; i!=n; i++) {
            if(((st[i].score[0]+st[i].score[1]+st[i].score[2]+st[i].score[3]+st[i].score[4])/5)>4)
            {
                cout<<st[i].fio<<endl;
                cout<<st[i].group<<endl;
            }
        }
    
    delete []st;
    return 0;
}
