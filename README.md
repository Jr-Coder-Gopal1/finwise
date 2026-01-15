# finwise
//this is an software made by me for financial service, this is just a prototype made by me(gopal) at the age of 14.
// A financial project made by Gopal sharma 13 yrs old. 2024-2025. FinWise 1.0;
//libraries



{
#include<iostream>
#include<ctime>
#include<algorithm>
#include<math.h>
#include<cctype>
#include<cstring>
#include<string>
#include<algorithm>
#include<vector>
#include<set>
#include<unistd.h>
#include<cmath>
#include<map>
#include<fstream>
#include<ctime>
#include <exception>
#include<iomanip>

//global variables
 long s;
 long incom;

//bool data types
bool is_over_budget(double budget, double expense) { return expense > budget; }
bool is_savings_low(double income, double savings) { return savings < (0.2 * income); }
bool has_high_debt(double debt, double income) { return debt > (0.5 * income); }
bool can_invest_in_stocks(double savings) { return savings > 1000; }
bool is_emergency_fund_adequate(double savings, double expense) { return savings >= (3 * expense); }
bool is_spending_on_luxury_high(double luxury_expense, double total_expense) { return luxury_expense > (0.3 * total_expense); }


//macros
#define reset "\033[0m"
#define red "\033[0;31m"
#define green "\033[1;32m"
#define yellow "\033[0;33m"
#define blue "\033[0;34m"
#define magenta "\033[0;35m"
#define cyan "\033[0;36m"
#define white "\033[1;37m"
#define black "\033[0;30m"
#define bright_red "\033[1;31m"
#define bright_green "\033[1;32m"
#define bright_yellow "\033[1;33m"
#define bright_blue "\033[1;34m"
#define bright_magenta "\033[1;35m"
#define bright_cyan "\033[1;36m"
#define bright_white "\033[1;37m"
#define bold "\033[1m"
#define underline "\033[4m"
#define inverted "\033[7m"
#define strikethrough "\033[9m"


//functions declaration
void main_page();
void choice(void);


using namespace std;

void financial_insights_and_reports(
    double income, double expense, double savings, 
    double budget, double debt, double luxury_expense) {
    
    double total_expense = expense;
    
    // Calculations
    double savings_percentage = (savings / income) * 100;
    double expense_percentage = (expense / income) * 100;
    double debt_ratio = (debt / income) * 100;
    double luxury_percentage = (luxury_expense / total_expense) * 100;

    // Recommendations (AI suggestions)
    cout << blue "\nAI Recommendations:\n" reset;
    if (expense > budget) {
        cout << red "Recommendation: " reset "Your expenses exceed your budget. Consider reducing spending.\n";
    }
    if (savings_percentage < 20) {
        cout << red "Recommendation: " reset "Your savings are below 20% of your income. Aim to save more.\n";
    }
    if (debt_ratio > 50) {
        cout << red "Recommendation: " reset "Your debt is over 50% of your income. Focus on debt repayment.\n";
    }
    if (savings > 1000) {
        cout << blue "Suggestion: " reset "You have sufficient savings to consider investing in stocks.\n";
    }
    if (savings < (3 * expense)) {
        cout << red "Warning: " reset "Your emergency fund is inadequate. Build it to cover at least 3 months of expenses.\n";
    }
    if (luxury_percentage > 30) {
        cout << yellow "Advice: " reset "Luxury expenses exceed 30% of your total spending. Consider cutting back.\n";
    }

    // Financial Report
    cout << green "\nFinancial Reports and Insights:\n" reset;

    cout << yellow "\nSummary Metrics:\n" reset;
    cout << " - Total Income: ₹" << fixed << setprecision(2) << income << endl;
    cout << " - Total Expense: ₹" << expense << " (" << fixed << setprecision(1) << expense_percentage << "% of income)\n";
    cout << " - Savings: ₹" << savings << " (" << savings_percentage << "% of income)\n";
    cout << " - Debt: ₹" << debt << " (" << debt_ratio << "% of income)\n";

    cout << yellow "\nExpense Breakdown:\n" reset;
    cout << " - Luxury Expenses: ₹" << luxury_expense << " (" << luxury_percentage << "% of total expenses)\n";
    cout << " - Non-Luxury Expenses: ₹" << total_expense - luxury_expense << endl;

    cout << yellow "\nInsights:\n" reset;
    if (expense > income) {
        cout << red " - Warning: " reset "Your expenses exceed your income. Consider reducing spending.\n";
    }
    if (savings_percentage < 20) {
        cout << red " - Advice: " reset "Your savings are below 20% of your income. Aim to save more.\n";
    }
    if (debt_ratio > 50) {
        cout << red " - Focus: " reset "Your debt is high. Try to prioritize debt repayment.\n";
    }
}
    int main(void){
        string e_mail , name_u , pass ;
        fstream income;
        income.open("income.txt", ios::in | ios::out | ios::app);
            fstream sign_in;
            sign_in.open("text_s.txt" , ios::in | ios::out | ios::app);
            if(!sign_in.is_open()){//checks if the file exist or not ; if not then creates a new file
                sign_in.open("text_s.txt" , ios::out);//creates the file automatically
                sign_in.close();
                sign_in.open("text_s.txt" , ios::in | ios::out | ios::app);//opens it with all the property
            }fstream username;
            username.open("username.txt" , ios::in | ios::out | ios::app);
            if(!username.is_open()){
                username.open("username.txt" , ios::out);
                username.close();
                username.open("username.txt" , ios::in | ios::out | ios::app);
            }if(!income.is_open()){
            income.open("income.txt" , ios::out);
            income.close();
            income.open("income.txt" , ios::in | ios::out | ios::app);
        }
            string data,name;
            getline(username,name);
            getline(sign_in, data);
            if ( data == "sign in"){
                cout<<green<<bold<<underline"\nWelcome back ! "<<red<<bold<<underline<<name<<reset<<endl;
                main_page();
                }else{
                        cout << "\n\033[1;32m=======================================\033[0m\n";
                         cout << "\033[1;36m           Welcome to FinWise\033[0m\n";  
                         cout << "\033[1;32m=======================================\033[0m\n";
                         cout << "\033[0;33m                Sign in                \033[0m\n";
                         cout << "\033[1;32m=======================================\033[0m\n";
                        cout<< blue << underline <<bold << "\nEnter your name: ";
                        getline(cin,name_u);
                        cout<<cyan<<underline<<bold<<"\nEnter your Email: ";
                        getline (cin , e_mail);
                        if (e_mail.find("@gmail.com")!=string::npos){
                            cout<<green<<bold<<underline<<"\nGreat!\n"<<yellow<<bold<<underline<<"\nEnter your password: ";
                            getline(cin,pass);
                            string fn=name_u.substr(0,name_u.find(" "));
                            username.clear();
                            username.seekp(0);
                            username<<fn<<endl;
                            username.close();
                            cout<<yellow<<bold<<"Your Monthly Income after tax!\n>>>"<<reset;
                            cin>>incom;
                            cin.ignore();
                            income.clear();
                            income.seekp(0);
                            income<<incom<<endl;
                            income.close();

                            sign_in.clear();
                            sign_in.seekp(0);
                            sign_in<<"sign in"<<endl;
                            sign_in.close();
                            main_page();
                        }else{
                            cout<<red<<bold<<underline<<inverted<<"\nWrong Email! Enter the data again ;("<<reset<<endl;
                            main();
                        }
                }

    }

void main_page(void){
         cout << "\033[1;32m=======================================\033[0m\n";
    cout << "\033[1;36m           Welcome to FinWise\033[0m\n";  
    cout << "\033[1;32m=======================================\033[0m\n";
    cout << "\033[0;33m   Your Personal AI-powered Finance\033[0m\n";  
    cout << "\033[0;33m                Manager\033[0m\n";
    cout << "\033[1;32m=======================================\033[0m\n";
    cout << "\033[0;36mPlease choose an option from the menu:\033[0m\n";

    cout << "\033[0;33m1. Expense Tracker\033[0m\n";  
    cout << "\033[0;33m2. Budgeting Assistant\033[0m\n";  
    cout << "\033[0;33m3. Savings Goal Tracker\033[0m\n";
    cout << "\033[0;33m4. Income Tracker\033[0m\n";
    cout << "\033[0;33m5. Financial Reports & Insights\033[0m\n";
    cout << "\033[0;33m6. AI-Powered Recommendations\033[0m\n";
    cout << "\033[0;31m7. Exit\033[0m\n";  

    cout << "\033[1;32m=======================================\033[0m\n";
    choice();
}

void choice(void){
    while (true){//infinite loop 
            int high=0;
            string input;
            cout<<bold<<yellow<<underline<<"\nWelcome to FinWise!\ninput the function down :D\n>>>"<<reset;
            getline(cin,input);
            if ( input == "1" || input == "Expence tracker" || input == "expence tracker" || input=="e t"){
                 cout <<red<< "========= Expense Tracker =========" <<reset<< endl;
                    vector<string>data;  
                    vector<int>indata;
                    string a ;
                    cout<<green<<bold<<"\nFood: ";
                    getline(cin,a);//gets the monthly expence for Food,grocery etc.
                    data.push_back(a);
                    cout<<bold<<green<<"\nEducation: "<<reset;//''
                    getline(cin , a);
                    data.push_back(a);
                    cout<<bold<<green<<"\nEntertainment: "<<reset;
                    getline( cin , a);
                    data.push_back(a);
                    cout<<green<<bold<<"\nOthers: "<<reset;
                    getline(cin , a);
                    data.push_back(a);
                    cout <<red<< "========= Expense Tracker =========" <<reset<< endl;
                    try{
                    for ( auto& asa : data){
                               indata.push_back(stoi(asa));
                    }
                    }catch(exception& ez){
                            cout << red << "Invalid input. Please enter numeric values only." << reset << endl;
                            return;
                    }
                    for ( auto at : indata){
                            if(at>=high){
                                high = at;
                            }
                    }
                    int percent =  (12 * high)/100;
                    cout <<red<< "\n\n========= Expense Tracker =========" <<reset<< endl;
                    cout << green << bold << "FinWise AI has Deeply Analysed the data and you can reduce "<< red<<bold<<percent<<green<<bold<<" rupees as your higest expence was of rupees : "<< red<<bold<<high<<bold<<blue<<underline<<". This AI report and suggestions will help you to increase your budget and allow you more money for investing to your dreams ! - FinWise AI\n"<<reset<<endl;
                    cout <<red<< "========= Expense Tracker =========" <<reset<< endl;

            }
                    else if( input == "7" || input == "exit" || input == "Exit" || input == "EXIT"){
                            cout<<bold<<red<<underline<<"Bye!! hope you enjoyed that"<<reset;
                            exit(1);
                    }
        else if ( input == "2" || input == "Budgeting assistant" || input == "budgeting assistant" || input == "ba")
        {
               fstream data_in_file;
                data_in_file.open("income.txt" , ios::out | ios::in | ios::app);
            if(!data_in_file.is_open()){
                data_in_file.open("income.txt" , ios::in | ios::out);
                data_in_file.close();
                data_in_file.open("income.txt" , ios::in | ios::out | ios::app);
                }      
           long income;
           data_in_file>>income;//gets the income from the file
           if (data_in_file.fail() || income <= 0) { // Validate income value
                    cout << red << "Invalid or missing income data. Please ensure the file contains a valid number." << reset << endl;
                    return;
                }
           float e = (15*income)/100;
           long f= (30*income)/100;
           long ee=(10*income)/100;
           long o=(25*income)/100;
           long savings = (20*income)/100;
           cout << bold << green << "\n=======================================\n";
           cout << cyan << "          Budgeting Assistant         \n";
           cout << green << "=======================================\n";

           cout << yellow << "Essentials (30%):      " << bright_green << f << " INR\n";
           cout << yellow << "Entertainment (15%):   " << bright_green << e << " INR\n";
           cout << yellow << "Education (10%):       " << bright_green << ee << " INR\n";
           cout << yellow << "Other Expenses (25%):  " << bright_green << o << " INR\n";
           cout << yellow << "Savings (20%):         " << bright_green << savings << " INR"<<red<<bold<<"\nTHIS BUDGET IS PROVIDED BY "<<blue<<bold<<"FinWise"<<green <<bold<<" AI"<<yellow<<bold<<" Powered by Gopal Softwares limited .\n"<<red<<bold<<" This is Monthly budget with acurate expences. ";

           cout << bold << green << "\n=======================================\n"<< reset;
           data_in_file.close();
        }//end of budget assistance
        else if ( input == "3" || input== "savings" || input =="Savings Goal Tracker" || input =="savings goal tracker" ||input=="sgt"||input=="SGT"||input=="s g t"||input=="Sgt"||input=="sGt"||input=="sgT"||input==" S g t"||input=="s G t"|| input=="s g T"|| input=="S G T"){
            fstream dr;
            dr.open("dream.txt",ios::in |ios::out|ios::app|ios::ate);
            if(!dr.is_open()){
                dr.open("dream.txt",ios::out);
                dr.close();
                dr.open("dream.txt",ios::in |ios::out|ios::app|ios::ate);
            }
            string data_dr;
            string dream;
            if(dr.tellg()>0){
                dr.clear();
                dr.seekg(0,ios::beg);
                
            getline(dr,data_dr);
                cout<<red<<bold<<"Fin"<<blue<<bold<<"Wise"<<green<<bold<<" AI"<<yellow<<bold<<" Keeps your dreems safe \nHere is the dream data:\n"<<data_dr;
            }else{
            cout << bold << magenta << "\n========= Savings Goal Tracker =========\n" << reset;
            long savings_goal, current_savings;
            cout<<bold<<green<<"Entert the name of your dream : "<<reset;
            getline(cin,dream);
            cout << bold << green << "Enter your savings goal (in INR): " << reset;
            cin >> savings_goal;
            cin.ignore();
            cout << bold << green << "Enter your current savings (in INR): " << reset;
            cin >> current_savings;
            cin.ignore();

            if (current_savings >= savings_goal) {
                cout << bold << green << "\nCongratulations! You've already achieved your savings goal!\n" << reset;
            } else {
                fstream data_in_fil;
                data_in_fil.open("income.txt", ios::in);
                if (!data_in_fil.is_open()) {
                    cout << red << "Error: Unable to open the income file!" << reset << endl;
                    return;
                }

                long incom;
                data_in_fil >> incom;
                data_in_fil.close();

                if (incom <= 0) {
                    cout << red << "Error: Invalid income data found in the file!" << reset << endl;
                    return;
                }

                long remaining = savings_goal - current_savings;
                long cu_sa;
                cout<<green<<bold<<"Enter your Monthly Savings: "<<reset;
                cin>>cu_sa;
                cin.ignore();
                float monthly_savings = cu_sa; // Assuming 20% of income goes into savings

                if (monthly_savings <= 0) {
                    cout << red << "Error: Monthly savings cannot be zero or negative. Check your income input!" << reset << endl;
                    return;
                }

                int months_required = ceil((float)remaining / monthly_savings);
                cout << bold << cyan << "\nYou need to save " << bold << white << remaining << " INR " << reset;
                cout << bold << cyan << "more to reach your goal.\n" << reset;
                int years=months_required/12;
                cout << bold << blue << "With your current income, it will take approximately " << bold << green << months_required << " month(s) or "<< red<<bold<<years <<bold<<blue<< "year(s)"<< reset;
                cout << bold << yellow << " to achieve your goal.\n" << reset;
                 dr.clear();
                 dr.seekp(0);
                 dr<<green<<bold<<"Dream: "<<dream<< " Months required : "<<months_required<< "  savings required: "<<remaining<<" and approximatily year(s) required to complete the goal: "<<years
                 
                 <<reset;
                 dr.close();
                 
            }

            cout << bold << magenta << "\n========================================\n" << reset;
               
           }
        }else if( input == "4" ||input == "income tracker"||input=="Income Tracker"||input=="Income tracker"||input=="IT"||input=="it"||input=="I T"){
            vector <string> category , date , source ;
            
            cout << bold << magenta << "\n========================================\n" << reset;
            cout<<red<<bold<<"             Income Tracker             "<<reset;
            cout << bold << magenta << "\n========================================\n" << reset;
            
            cout << bold << magenta << "\n\n\n========================================\n" << reset;
            vector <int> salary;
            fstream ffile;
            cout<<magenta<<bold<<"Enter the Number of entries you need for your income: "<<reset;
            int entr;
            cin>>entr;
            cin.ignore();
            string s ,d ,c;
            int inc;
            for(int i = 0 ; i < entr ; i++){
                    cout<<blue<<bold<<"Enter the source for the Entry no. "<<i+1<<": "<<reset;
                    getline(cin,s);
                    source.push_back(s);
                    cout<<blue<<bold<<"Enter the date of joining it : "<<reset;
                    getline(cin , d);
                    date.push_back(d);
                    cout<<blue<<bold<<"Enter the salary : "<<reset;
                    cin>>inc;
                    cin.ignore();
                    salary.push_back(inc);
                    cout<<magenta<<bold<<"Enter the category for the job: "<<reset;
                    getline(cin,c);
                    category.push_back(c);
            }
            ffile.open("current.txt" , ios::in |ios::out |ios::app);
              if(!ffile.is_open()){
                    ffile.open("current.txt",ios::out);
                    ffile.close();
                    ffile.open("current.txt", ios::in|ios::out|ios::app);
              }
              int dab;
              ffile>>dab;
            int earned=dab;
            cout<<red << bold <<"The money you earned is : \n";
            for(long va : salary){
                earned+=va;
            }cout<<magenta<<bold<<"You earned total of ₹ \n"<<earned<<endl;
            cout<<green<<bold<<"The Dates were: ";
            for ( auto db : date){
                cout<<blue<<bold<<"["<<db<<"]"<<"\n";
            }cout<<magenta<<bold<<"The sources were : \n";
            for (auto scr: source){
                cout<<cyan<<bold<<scr<<"\n";
            }cout<<bold<<"The Categories were : \n";
            for( auto m : category){
                cout<<magenta<<bold<<m<<"\n";
            
            }
            
            cout << bold << magenta << "\n========================================\n" << reset;
        }else if (input == "5"||input == "Financial Reports" || input == "Insights" || input == "Reports" || input == "financial reports" || input == "insights" || input == "reports" || input == "Financial Reports and Insights" || input == "Financial Insights" || input == "financial insights" || input == "financialreports" || input == "financialinsights" || input == "ReportsAndInsights" || input == "reportsandinsights" || input == "financial reports insights" || input == "Financial Reports Insights" || input == "FRI" || input == "fri"){
              
    cout << blue "fin" red "wise" yellow "ai" reset " - AI-powered financial advisor\n\n";

    double income, expense, savings, budget, debt, luxury_expense;

    // Prompt the user to input values
    cout << "Enter your total income (in ₹): ";
    cin >> income;
    cout << "Enter your total expense (in ₹): ";
    cin >> expense;
    cout << "Enter your savings (in ₹): ";
    cin >> savings;
    cout << "Enter your budget (in ₹): ";
    cin >> budget;
    cout << "Enter your total debt (in ₹): ";
    cin >> debt;
    cout << "Enter your luxury expense (in ₹): ";
    cin >> luxury_expense;
    // Call the function
    financial_insights_and_reports(income, expense, savings, budget, debt, luxury_expense);

        }
        else if ( input == "AI" || input =="6" || input == "AI-Powered Recommendations" || input=="AI Powered Recommendations"||input=="AIPoweredRecommendations"||input=="AI-powered recommendations"||input=="ai p r"){
            
    cout << blue "fin" red "wise" yellow " ai" reset <<bold blue" - AI-powered financial advisor\n\n";

    // User inputs
    double income, expense, savings, budget;
    double debt, luxury_expense, total_expense;

    cout <<blue<<bold<< "Enter your monthly income: ";
    cin >> income;
    cin.ignore();
    cout <<blue<<bold<< "Enter your monthly expense: ";
    cin >> expense;
    cin.ignore();
    cout <<blue<<bold<< "Enter your current savings: ";
    cin >> savings;
    cin.ignore();
    cout <<blue<<bold<< "Enter your monthly budget: ";
    cin >> budget;
    cin.ignore();
    cout <<blue<<bold<< "Enter your current debt: ";
    cin >> debt;
    cin.ignore();
    cout <<blue<<bold<< "Enter your luxury expenses: ";
    cin >> luxury_expense;
    cin.ignore();
    cout <<blue<<bold<< "Enter your total monthly expenses: ";
    cin >> total_expense;
    cin.ignore();

    // Evaluate conditions
    if (is_over_budget(budget, expense)) {
        cout << red "Recommendation: " reset << bold<<cyan"Your expenses exceed your budget. Consider reducing spending.\n";
    }
    if (is_savings_low(income, savings)) {
        cout << red "Recommendation: " reset<<bold<<cyan "Your savings are below 20% of your income. Aim to save more.\n";
    }
    if (has_high_debt(debt, income)) {
        cout << red "Recommendation: " reset <<bold<<cyan"Your debt is over 50% of your income. Focus on debt repayment.\n";
    }
    if (can_invest_in_stocks(savings)) {
        cout << blue "Suggestion: " reset <<bold<<cyan"You have sufficient savings to consider investing in stocks.\n";
    }
    if (!is_emergency_fund_adequate(savings, expense)) {
        cout << red "Warning: " reset <<bold<<cyan"Your emergency fund is inadequate. Build it to cover at least 3 months of expenses.\n";
    }
    if (is_spending_on_luxury_high(luxury_expense, total_expense)) {
        cout << yellow "Advice: " reset <<bold<<cyan"Luxury expenses exceed 30% of your total spending. Consider cutting back.\n";
    }
        }
    } 
}
}
