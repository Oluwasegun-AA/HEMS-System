/* This program controls the charging cycle of the battery while measuring the battery's State of charge
it also ensures Power is made constantly available by switing to the next available Powere source with
with preference for the renewable source
*/

#include <iostream>
#include <windows.h>
#include <string>
#include <stdio.h>
#include <time.h>
#include<conio.h>
#include<sstream>
#include<cstdio>
using namespace std;

int main(int argc, char**argv)
{int SOC;
string  PV;
char Input = 'D';
        cout << "                          ***********************************************************" << endl;
        cout << "                          * This program controls the charging cycle of the battery *" << endl;
        cout << "                          * while measuring the battery's state of charge, and also *" << endl;
        cout << "                          * ensures power is made constantly available by switching *" << endl;
        cout << "                          * to the next available Power source with preference for  *" << endl;
        cout << "                          * the renewable source                                    *" << endl;
        cout << "                          ***********************************************************" << endl;
        cout << "                                            *     Created by      *" << endl;
        cout << "                                            *  Adepoju Oluwasegun *" << endl;
        cout << "                                            ***********************" << endl; 
        Sleep(2000);
		cout<< "Query PV . . . .\r";             
        Sleep(2000);
label1: cout<<"PV ON?  (Y/N)"<<endl;
label3: cin>>Input;
        
   switch(Input)
   {
   case 'Y' :
   	 goto label2; 
      break;
   case 'y' :
   	 goto label2;
   	 break;
   case 'n':
   	cout << "\t\t\tRENEWABLE ENERYGY SOURCE UNAVAILABLE" << endl;
      Sleep(3000);
      cout<<"\t\t\t.......BATTERY NOT CHARGING......."<<endl;
      goto label1;
      break;
   case 'N' :
      cout << "\t\t\tRENEWABLE ENERYGY SOURCE UNAVAILABLE" << endl;
      Sleep(3000);
      cout<<"\t\t\t.......BATTERY NOT CHARGING......."<<endl;
      goto label1;
      break;
      
   default :
      cout << Input<< " is not a valid input" << endl;
      goto label3;
      
   }
         label2: cout<<"\nQuery Battery's' SOC\r";
        Sleep(2000);
        cout<<"Percentage State of charge  ";
        cin>> SOC;
        if (SOC <90)
{
    HANDLE handle = GetStdHandle(STD_OUTPUT_HANDLE);
	SetConsoleTextAttribute( handle, 14 );
	cout<< "\t\t\tBATTERY CHARGING INITIALISING..\r";
	Sleep(500);
	cout<< "\t\t\tBATTERY CHARGING INITIALISING...\r";
	Sleep(500);
	cout<< "\t\t\tBATTERY CHARGING INITIALISING....\r";
	Sleep(500);
	cout<< "\t\t\tBATTERY CHARGING INITIALISING.....\r";
	Sleep(500);
	cout<< "\t\t\tBATTERY CHARGING INITIALISING......\r";
	Sleep(500);
	cout<< "\t\t\tBATTERY CHARGING INITIALISING.......\r";
	Sleep(2000);
	cout<< "\t\t\t\a\a\a\a\a\a\a\a\a.......BATTERY CHARGING.......\a\a\a\a\a\a\a\a\a"<<endl;
	cout<<"\n\n\n\t\t\t____________________________________"<<endl;
	cout<<"\t\t\t\t BATTERY IN USE "<<endl;
	goto label1;
}
	else if (SOC >= 99)
	{ 
	HANDLE handle = GetStdHandle(STD_OUTPUT_HANDLE);
    SetConsoleTextAttribute( handle, 12 );
	cout<< "\t\t\t\tBATTERY FULL!\n"<<"\t\t\t..... CHARGING STOPPED ....."<<endl;
	goto label1;
	
}
	}

yello = 14 battery charging
red = 12 warning
white= 15 input
purple= 13  battery in use