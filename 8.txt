#include <iostream>
#include<string>

class Student{
public:
    friend std::ostream& operator<<(std::ostream& out,const Student& student);
    friend std::istream& operator>>(std::istream& in,Student& student);
    Student operator=(const Student &student);
private:
    std::string name,group;
    float score;
    int debt;
};
  std::ostream& operator<<(std::ostream& out,const Student& student){
    out <<student.name<<' '<<student.group<<' '<<student.score<<' '<<student.debt<<std::endl;
    return out;
}

Student Student::operator=(const Student &student) {
    this->name = student.name;
    this->group = student.group;
    this->score = student.score;
  }
 std::istream& operator>>(std::istream& in,Student& student){
     in>>student.name;
     in>>student.group;
     in>>student.score;
     in>>student.debt;
     return in;

  }
void number(Student *& a,int n ){
       a=new Student[n];
  }

int main() {
    int f =1; float newscore=3.1;
    Student* student;
    int n;
    std::cout<<"Введите число студентов:"<<" "<<std::endl;
    std:: cin>>n;
    number(student,n);
    std::cout<<"Введите имя студента, группу, оценку и количество долгов:"<<" "<<std::endl;

    for(int i=0;i<n;i++){
        std::cout<<i+1<<"-й:"<<" ";
        std::cin>>student[i];
    }
    for(int i=0;i<n;i++){
        std::cout<<i+1<<"-й:"<<" ";
        std::cout<<student[i];
    }
    student[1] = student[2];
    std::cout<<student[1];
    return 0;
}
