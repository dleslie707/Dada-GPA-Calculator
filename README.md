// # Dada GPA Calculator
//
//  main.cpp
//  testing
//
//  Created by Daequan Leslie on 10/29/19.
//  Copyright © 2019 Dada. All rights reserved.
//

#include <iostream>
    
#include <string>

struct Course{
    
    std::string name;
    double grade;
    std::string lettergrade;
    double credits;
    
};


int main(){
    
    
    int size;
   
    std::cout << "Dada GPA Calculator \n";
    
    std::cout<< "Please enter number of classes";
    
    std::cin>> size;
    
    Course* c = nullptr;
    
    c = new Course[size];
    
    delete[] c;
    
    char again = 'Y';
  

    for( int i =0; i<size; i++)
    {
        
        std::cout << " \n Enter the name of course: \n";
        std::cin.ignore (std::numeric_limits<std::streamsize>::max(), '\n');
        std::getline(std::cin, c[i].name);
        
        
        do{
            
            std::cout << "Please enter a grade" <<std::endl;
            while (!(std::cin >> c[i].grade)){
                std::cout << "Must Be A Number:" <<std::endl;
                std::cin.clear();
                std::cin.ignore(100, '\n');
            }
            
            if( (c[i].grade>=97) && (c[i].grade <=100) )
            {
                std::cout << "Your lettergrade is: A+" << std::endl;
                c[i].lettergrade = "A+";
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
            }
            
            else if ( (c[i].grade>=93) && (c[i].grade <=96) )
            {
                std::cout << "Your lettergrade is: A" << std::endl;
                c[i].lettergrade = "A";
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
            }
            
            else if ( (c[i].grade>=90) && (c[i].grade <=92) )
            {
                std::cout << "Your lettergrade is: A-" << std::endl;
                c[i].lettergrade = "A-";
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
            }
            
            else if ( (c[i].grade>=87) && (c[i].grade <=89) )
            {
                std::cout << "Your lettergrade is: B+" << std::endl;
                c[i].lettergrade = "B+";
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
            }
            
            else if ( (c[i].grade>=83) && (c[i].grade <=86) )
            {
                std::cout << "Your lettergrade is: B" << std::endl;
                c[i].lettergrade = "B";
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
            }
            
            else if ( (c[i].grade>=80) && (c[i].grade <=82) )
            {
                std::cout << "Your lettergrade is: B-" <<std::endl;
                c[i].lettergrade = "B-";
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
            }
            
            else if ( (c[i].grade>=77) && (c[i].grade <=79) )
            {
                std::cout << "Your lettergrade is: C+" <<std::endl;
                c[i].lettergrade = "C+";
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
            }
            
            else if ( (c[i].grade>=73) && (c[i].grade <=76) )
            {
                std::cout << "Your lettergrade is: C" <<std::endl;
                c[i].lettergrade = "C";
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
            }
            
            else if ( (c[i].grade>=70) && (c[i].grade <= 72) )
            {
                std::cout << "Your lettergrade is: C-" <<std::endl;
                c[i].lettergrade = "C-";
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
            }
            else if ( (c[i].grade>=67) && (c[i].grade <=69) )
            {
                std::cout << "Your lettergrade is: D+" <<std::endl;
                c[i].lettergrade = "D+";
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
            }
            
            else if ( (c[i].grade>=60) && (c[i].grade <=66) )
            {
                std::cout << "Your lettergrade is: D" <<std::endl;
                c[i].lettergrade = "D";
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
            }
            
            else if ( (c[i].grade>=0) && (c[i].grade <=59) )
            {
                std::cout << "Your lettergrade is: F" <<std::endl;
                c[i].lettergrade = "F";
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
            }
            else
            {
                std::cout << "Your no fun" <<std::endl;
                std::cout<< "Go again? (y/n): ";
                std::cin >> again;
                
            }
        }while (again == 'y' || again == 'Y');
        
        std::cout << " \n Enter the amount of credits: \n";
        while (!(std::cin >> c[i].credits)){
            std::cout <<std::endl << "Must Be A Number:" <<std::endl;
            std::cin.clear();
            std::cin.ignore(100, '\n');
        }
    }
    
    for(int q=0; q<size; q++){
        std::cout<< "Course" << '\t' << '\t' <<(q+1) << std::endl;
        std::cout<< "Name: " << c[q].name << '\t' << '\t' << std::endl;
        std::cout<< "Grade: " << c[q].grade << '\t' << '\t' << std::endl;
        std::cout<< "Letter Grade: " << c[q].lettergrade << '\t' << '\t' << std::endl;
        std::cout<< "Credit(s): " << c[q].credits << '\t' << '\t' << std::endl << '\t' << '\t';
    }
    
    double gpa = 0;
    int totalscore = 0;
    int totalcredits = 0;
    for(int q=0; q<size; q++){
        totalscore = totalscore+(c[q].grade* c[q].credits);
        totalcredits = totalcredits+c[q].credits;
    }
    gpa = totalscore/totalcredits;
    
    std::cout << "The GPA comes out to: " << gpa <<"%" << std::endl;
    return 0;
}
