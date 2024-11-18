CGPA Calculator in C++

This is a simple CGPA Calculator written in C++. It allows users to input their marks, credit hours, and corresponding grade points for each subject and calculates their Cumulative Grade Point Average (CGPA) based on the weighted average method.
Features

    Allows input for multiple subjects.
    Calculates CGPA based on user inputs.
    Supports custom credit hours for each subject.
    Displays the final CGPA in real-time.

Prerequisites

To run this program, you need a C++ compiler such as:

    GCC for Linux/MacOS.
    MinGW for Windows.
    Clang for macOS (optional).
    Any C++ IDE or online compiler (e.g., Replit, OnlineGDB).

Installation
1. Clone the Repository

Clone this repository to your local machine using the following command:

git clone https://github.com/yourusername/cgpa-calculator.git

2. Navigate to the Project Folder

cd cgpa-calculator

3. Compile the C++ Code

To compile the C++ program, use the following command:

g++ cgpa_calculator.cpp -o cgpa_calculator

This will create an executable named cgpa_calculator (or cgpa_calculator.exe on Windows).
4. Run the Program

Now, you can run the program using:

./cgpa_calculator

Usage

When you run the program, it will prompt you to:

    Enter the number of subjects: Specify how many subjects you want to enter for the CGPA calculation.
    Enter the subject details: For each subject, input:
        The subject name.
        The credit hours for the subject.
        The grade point (on a scale of 4.0).

After inputting all the data, the program will calculate and display your CGPA.
Example Input/Output
Input:

Enter the number of subjects: 3

Enter details for Subject 1:
Name: Math
Credit Hours: 3
Grade Point (on a scale of 4.0): 3.7

Enter details for Subject 2:
Name: Physics
Credit Hours: 4
Grade Point (on a scale of 4.0): 3.5

Enter details for Subject 3:
Name: Chemistry
Credit Hours: 3
Grade Point (on a scale of 4.0): 3.8

Output:

Your CGPA is: 3.68

Example Code

Here is a brief look at the program's code:

#include <iostream>
#include <vector>
using namespace std;

struct Subject {
    string name;
    int creditHours;
    float gradePoint;
};

float calculateCGPA(const vector<Subject>& subjects) {
    float totalCredits = 0;
    float weightedGradePoints = 0;
    
    for (const auto& subject : subjects) {
        weightedGradePoints += subject.creditHours * subject.gradePoint;
        totalCredits += subject.creditHours;
    }
    
    return weightedGradePoints / totalCredits;
}

int main() {
    int numSubjects;
    
    cout << "Enter the number of subjects: ";
    cin >> numSubjects;
    
    vector<Subject> subjects(numSubjects);
    
    for (int i = 0; i < numSubjects; ++i) {
        cout << "\nEnter details for Subject " << i + 1 << ":\n";
        cout << "Name: ";
        cin >> subjects[i].name;
        
        cout << "Credit Hours: ";
        cin >> subjects[i].creditHours;
        
        cout << "Grade Point (on a scale of 4.0): ";
        cin >> subjects[i].gradePoint;
    }
    
    float cgpa = calculateCGPA(subjects);
    
    cout << "\nYour CGPA is: " << cgpa << endl;

    return 0;
}

License

This project is open-source and available under the MIT License.
Contributing

If you'd like to contribute to this project, feel free to fork the repository, make changes, and submit a pull request.
Steps to contribute:

    Fork the repository
    Clone your forked repository
    Create a new branch (git checkout -b feature-branch)
    Make changes and commit (git commit -am 'Add new feature')
    Push to your branch (git push origin feature-branch)
    Submit a pull request
