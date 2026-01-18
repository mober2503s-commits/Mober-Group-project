#include<iostream> 
using namespace std; 
 
 
double validate(int amount){ 
    while (amount<0) 
    { 
        cout<<"enter the amount again: "<<endl; 
        cin>>amount; 
    } 
    return amount; 
    
    
} 
 
int main(){ 
    int months; 
    double annualtax,balance; 
 
    cout<<"enter balance: "<<endl; 
    cin>>balance; 
 
    cout<<"enter anual tax rate: "<<endl; 
    cin>>annualtax; 
 
    cout<<"enter number of months: "<<endl; 
    cin>>months; 
 
    double deposit[months]; 
    double withdraw[months]; 
    double tax[months]; 
 
    double totalDeposit = 0; 
    double totalWithdraw = 0; 
    double totalTax = 0; 
 
    double monthlytaxrate=(annualtax/100)/12; 
 
    for (int count = 0; count < months; count++) 
    { 
        cout<<"Month "<<count+1<<endl; 
 
        cout<<"enter the deposited amount: "<<endl; 
        cin>>deposit[count]; 
        deposit[count]=validate(deposit[count]); 
        balance=balance+deposit[count]; 
        totalDeposit=totalDeposit+deposit[count]; 
 
        cout<<"enter withdrawal amount: "<<endl; 
        cin>>withdraw[count]; 
        withdraw[count]=validate(withdraw[count]); 
        balance=balance-withdraw[count]; 
        totalWithdraw=totalWithdraw+withdraw[count]; 
 
        tax[count]=balance*monthlytaxrate; 
        balance=balance-tax[count]; 
        totalTax=totalTax+tax[count]; 
 
    } 
 
    cout<<"Account summary: "<<endl; 
    cout<<"Final Balance: "<<balance<<endl; 
    cout<<"Total Deposited: "<<totalDeposit<<endl; 
    cout<<"Total Withdrawl: "<<totalWithdraw<<endl; 
    cout<<"Total Tax: "<<totalTax<<endl; 
 
 
}


# Mober-Group-project
Group project about TAX calculator
