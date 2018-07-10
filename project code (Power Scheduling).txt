#include <iostream>
#include <iomanip>
#include <string>
#include <cmath>
#include <string>
#include <sstream>
#include <stdio.h>
#include <time.h>
#include<conio.h>
#include<windows.h>
using namespace std;

// Get current date/time, format is YYYY-MM-DD.HH:mm:ss
const string currentDateTime() {
    time_t     now = time(0);
    struct tm  tstruct;
    char       buf[80];
    tstruct = *localtime(&now);
    // Visit http://en.cppreference.com/w/cpp/chrono/c/strftime
    // for more information about date/time format
    strftime(buf, sizeof(buf), "%Y-%m-%d . %X", &tstruct);

    return buf;
}
//helper function declarations
int calcDaysSoFar( int year, int month );
bool isLeapYear( int year);
void printCalendar(int month /*1 = January*/, int year, int firstDay /* 0 = Sunday*/);
void printGridTop(int innerWidth);
void repeatChar(char ch, int numChar);
void drawDivider(int innerWidth);
void printGridBottom(int innerWidth);


//Globals
 const int firstYear = 1800; //This is our start point
 const int dayOffset = 3; //The first day of our start year may not be a Sunday ( in 1800 it was Wednesday)
 const int firstLeapYear = 1804; //help to reduce how many leap years we have to check
 
 string dayNames[] = {"Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"};
 
 string  months[] = { "January", "February", "March", "April", "May", "June", "July", "August", 
        "September", "October", "November", "December"};

 int daysInMonth[] = { 31,28,31,30,31,30,31,31,30,31,30,31} ; //standard year
 
 int daysPassed[] = { 0, 31, 59, 90, 120, 151, 181, 212, 243, 273, 304, 334}; //per month per year

int main ()

{
HANDLE handle = GetStdHandle(STD_OUTPUT_HANDLE);
    int year, month;
    int days;
    char a;
    char hyphen;
    int b;
    char c;
    int tyme;
    int Pload;
    int hawa;
    int mini;
    char R_ansa;
    time_t current = time(0);

  time_t currentTime;
  struct tm *localTime;

  time( &currentTime );                   // Get the current time
  localTime = localtime( &currentTime );  // Convert the current time to the local time

  int Dy    = localTime->tm_mday;
  int Mon  = localTime->tm_mon + 1;
  int Ye   = localTime->tm_year + 1900;
  int Hour   = localTime->tm_hour;
  int Min    = localTime->tm_min;
  int Sec    = localTime->tm_sec;
  
  
        cout << "                            ***********************************************************" << endl;Sleep(100);
        cout << "                            * This program Manages energy usage by sheduling various  *" << endl;Sleep(100);
        cout << "                            * preclassified loads for use at certain hours of the day *" << endl;Sleep(100);
        cout << "                            * with respect to some predefined rules, based on user's  *" << endl;Sleep(100);
        cout << "                            * preference                                              *" << endl;Sleep(100);
        cout << "                            ***********************************************************" << endl;Sleep(100);
        cout << "                                              *     Created by      *" << endl;Sleep(100);
        cout << "                                              *  Adepoju Oluwasegun *" << endl;Sleep(100);
        cout << "                                              ***********************" << endl; Sleep(2000);
  
  
labelx: cout<<" \n\n\t\t\tPress 1 to Schedule Load using the System's preset Date/Time \n\t\t\t\t\t             Or\n\t\t      Press any other key to run the Load Schedule of a desired date/time\n"<<endl;
    cin>>b;
    
    	if (b > 1)
	{       cout<<"\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t| #Note. You can only run a single protocol in this mode|"<<endl;
	        cout<<"\t\t\t|           when a desired time is selected             |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
	        SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
            cout<<"\t\t\t|_______________________________________________________|";
            SetConsoleTextAttribute( handle,  15);
	cout<<"\n\nPlease enter desired date (dd-mm-yyyy)\n";
   cin>>days>>hyphen>>month>>hyphen>>year;
   while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin >>days>>hyphen>>month>>hyphen>>year;
		}
	}
   else if (b == c)
	{ cout<<"Please enter desired date (dd-mm-yyyy)\n";
   cin>>days>>hyphen>>month>>hyphen>>year;
   while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');}
		cin >>days>>hyphen>>month>>hyphen>>year;
		
   goto label2;
	}

	else if(b == 1) 
	{
	goto label1;
	}

cout<<" \n\nPress 1 to use the System's preset time or any other key to enter a desired time \n"<<endl;
    cin>>b;
    if (b > 1)
	{cout<<"Please enter desired Time (HH:MM)\n";
   cin>>hawa>>hyphen>>mini;
   while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>hawa>>hyphen>>mini;
		}
	}
   else if (b == c)
	{ cout<<"Please enter desired Time (HH:MM)\n";
   cin>>hawa>>hyphen>>mini;;
   while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');}
		cin>>hawa>>hyphen>>mini;		
          while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>hawa>>hyphen>>mini;
		} ;
     	}

	else if(b == 1) 
	{	
cout<<" \n\t\t\tthe time is "<<Hour<<":"<<Min<<"\n";
goto labelk;

	}

 Hour = hawa;

label1: days=Dy;
		month=Mon;
		year=Ye;
	
  
label2:	  while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}

labelk: int mont[] = {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};
    char* da[] = {"Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"};   
    int d= days, m = month, y= year, i; 
    
           //do{
    //Calculate how many days have passed since Jan 1 of Start year to start of requested year & month
    days = calcDaysSoFar(year, month);
    int firstDayOfWeek = days % 7;
    
    printCalendar(month, year, firstDayOfWeek);
    //month++;
    //}while(month < 13); //need to be 13 because months are numbered 1 - 12


    // correction for leap year
    if (y % 4 == 0 && (y % 100 != 0 || y % 400 == 0))
        mont[1] = 29;
    if (y < 1900 || m < 1 || m > 12 || d < 1 || d > mont[m - 1]) {
    	SetConsoleTextAttribute( handle,  12);
        printf("Please Enter a valid input as Illustrated above\n");
        SetConsoleTextAttribute( handle,  15);
        return 1;
    }

    for (i = 1900; i < y; i++)
        if (i % 4 == 0 && (i % 100 != 0 || i % 400 == 0))
            d += 366;
        else
            d += 365;

    for (i = 0; i < m - 1; i++) 
        d += mont[i];

    printf("\nToday is a %s.\n\n", da[d % 7]);
    if (d%7 == 0 || d%7 == 6)
     
    {cout<< da[d%7]<< " is categorised as weekend";
    Sleep(2000);
    	}
	else{cout<< da[d%7]<< "  is categorised as a week day";
	Sleep(2000);
		}
    cout << "\t\t\t\tDevice  Date/Time =  " << currentDateTime() <<endl;
    Sleep(2000);
    
    if (d%7 == 0 || d%7 == 6)
{	cout<<"\n\n\t\t\t\t\tWEEKEND MODE ACTIVATED \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<<"\t\t\t\t  WEEKEND MODE ACTIVATED \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<<"\t\t\t\t  WEEKEND MODE ACTIVATED \r";
           Sleep(1000);
           goto label4;
		   
}
 else 
 {cout<<"\n\n\t\t\t\tWEEKEND MODE ACTIVATED \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<<"\t\t\t\t   WEEK DAYS PROTOCOL ACTIVATED \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<<"\t\t\t\t   WEEK DAYS PROTOCOL ACTIVATED \r";
           Sleep(1000);
           goto label5;
           
 }


label4: if((Hour == 20) || (Hour ==21)||(Hour == 22) || (Hour ==23)||(Hour == 24) || (Hour ==0)||(Hour == 1) || (Hour ==2)||(Hour == 3))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L4   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L4   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L4   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L4   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 2045)
		{goto label4;
		}
	else if(Pload > 2045)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  SetConsoleTextAttribute( handle,  14);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labela:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\t\t\tshutting down in 1  second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\t\t..........................................";
			   	cout<<"\n\t\t\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labela;
				   	break;
				   }
				   	
				  }	}

else if((Hour == 4) || (Hour ==6))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 3845)
		{goto label4;
		}
	else if(Pload > 3845)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelb:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelb;
				   	break;
				   }
				   	
				  }	}
		else if(Hour == 5) 
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4, L7   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4, L7   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4, L7   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4, L7   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 5345)
		{goto label4;
		}
	else if(Pload > 5345)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelc:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelc;
				   	break;
				   }
				   	
				  }	}
		
else if((Hour == 14) || (Hour == 15))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L3, L4, L7   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L3, L4, L7   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L3, L4, L7   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L3, L4, L7   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 3765)
		{goto label4;
		}
	else if(Pload > 3765)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			 cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labeld:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labeld;
				   	break;
				   }
				   	
				  }	}
		
else if((Hour == 18) || (Hour ==19))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 3645)
		{goto label4;
		}
	else if(Pload > 3645)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labele:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labele;
				   	break;
				   }
				   	
				  }	}
		
else if(Hour == 7)
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L5   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L5   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L5   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L5   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 2685)
		{goto label4;
		}
	else if(Pload > 2685)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelf:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelf;
				   	break;
				   }
				   	
				  }	}
		
else if((Hour == 8) || (Hour ==9)||(Hour==10)||(Hour==11))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L5, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L5, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L5, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L5, L8   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 3265)
		{goto label4;
		}
	else if(Pload > 3265)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelg:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelg;
				   	break;
				   }
				   	
				  }	}
		
else if((Hour == 12) || (Hour ==13))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L4, L5, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L4, L5, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L4, L5, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L4, L5, L8   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 3465)
		{goto label4;
		}
	else if(Pload > 3465)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelh:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelh;
				   	break;
				   }
				   	
				  }	}
		
else if(Hour == 16)
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L8   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 2135)
		{goto label4;
		}
	else if(Pload > 2135)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labeli:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labeli;
				   	break;
				   }
				   	
				  }	}
		
else if(Hour == 17)
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 3845)
		{goto label4;
		}
	else if(Pload > 3845)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelj:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelj;
				   	break;
				   }
				   	
				  }	}
				  
label5 :	if((Hour == 20) || (Hour ==21)||(Hour == 22) || (Hour ==23)||(Hour == 24) || (Hour ==0)||(Hour == 1) || (Hour ==2)||(Hour == 3))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L4   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L4   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L4   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L4   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 2045)
		{goto label5;
		}
	else if(Pload > 2045)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  SetConsoleTextAttribute( handle,  14);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelK:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\t\t\tshutting down in 1  second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\t\t..........................................";
			   	cout<<"\n\t\t\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelK;
				   	break;
				   }
				   	
				  }	}

else if((Hour == 4) || (Hour ==6))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 3845)
		{goto label5;
		}
	else if(Pload > 3845)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelL:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelL;
				   	break;
				   }
				   	
				  }	}
		else if(Hour == 5) 
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4, L7   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4, L7   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4, L7   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3, L4, L7   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 5345)
		{goto label5;
		}
	else if(Pload > 5345)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelm:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelm;
				   	break;
				   }
				   	
				  }	}
		
else if((Hour == 14) || (Hour == 15))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L3, L4, L7   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L3, L4, L7   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L3, L4, L7   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L3, L4, L7   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 3765)
		{goto label5;
		}
	else if(Pload > 3765)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			 cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labels:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labels;
				   	break;
				   }
				   	
				  }	}
		
else if((Hour == 18) || (Hour ==19))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L2, L3   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 3645)
		{goto label5;
		}
	else if(Pload > 3645)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labeln:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labeln;
				   	break;
				   }
				   	
				  }	}
		
else if((Hour == 7)||(Hour==16))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 1185)
		{goto label5;
		}
	else if(Pload > 1185)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t    Please Disconnect Excess / Unused Loads";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelo:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelo;
				   	break;
				   }
				   	
				  }	}
		
else if((Hour == 8) || (Hour ==9)||(Hour==10)||(Hour==11))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L8   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 1765)
		{goto label5;
		}
	else if(Pload > 1765)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelp:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelp;
				   	break;
				   }
				   	
				  }	}
		
else if((Hour == 12) || (Hour ==13))
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L4, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L4, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L4, L8   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L4, L8   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 1965)
		{goto label5;
		}
	else if(Pload > 1965)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelq:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelq;
				   	break;
				   }
				   	
				  }	}
		
else if(Hour == 17)
 {if ((Hour == 3) || (Hour == 23))
{cout<<"\n\n\t\t\twe are in the "<<Hour<<"rd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L3   SELECTED ";
SetConsoleTextAttribute( handle,  15);

}
else if ((Hour == 2) || (Hour ==22))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"nd"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L3   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else if ((Hour == 1) || (Hour == 21))
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"st"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L3   SELECTED ";
SetConsoleTextAttribute( handle,  15);
}
else  
{cout<<"\n\n\t\t\t\twe are in the "<<Hour<<"th"<<" hour of the day\n";
Sleep(1000);
SetConsoleTextAttribute( handle,  14);
cout<<"\n\t\t\t\t   LOAD   L1, L3   SELECTED \n";
SetConsoleTextAttribute( handle,  15);
}

       Sleep(2000);
cout<< "\nQuery Pload..                                                                                         \r";             
        Sleep(2000);
cout<<"Total Load (Watt)? =  ";
cin>>Pload;
 while(cin.fail()) 
		{
		cin.clear();
		cin.ignore(100, '\n');
		SetConsoleTextAttribute( handle,  12);
		cout << "Please enter a valid Input!\n";
		SetConsoleTextAttribute( handle,  15);
		cin>>days>>hyphen>>month>>hyphen>>year;
		}
	cout<<"Total Load is "<<Pload<<"Watt";
	if (Pload < 2985)
		{goto label5;
		}
	else if(Pload > 2985)
		{  cout<<"\n\t\t\t _______________________________________________________"<<endl;
	        cout<<"\t\t\t|             LOAD EXCEEDS ALLOWED LIMIT                |"<<endl;
         	cout<<"\t\t\t|_______________________________________________________|"<<endl;
		 SetConsoleTextAttribute( handle,  12);
		    cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       | \r";
            Sleep(500);
            cout<< "\a\t\t\t                                                                      \r";
            Sleep(500);
            cout<< "\a\t\t\t|                      WARNING!!!                       |\n";
			  cout<<"\t\t\t|_______________________________________________________|";
			  SetConsoleTextAttribute( handle,  15);
			  Sleep(1000);
			  cout<<"\n\n\t\t\t\t\t    LOAD L1 ACTIVATED";
			  Sleep(2000);
			  cout<< "\nRESET? (Y/N) = ";
labelr:	  cin>>R_ansa;
		  switch (R_ansa)
			  {case 'y':
			  	goto labelx;
			  	break;
			   case 'Y':
			   	goto labelx;
			  	break;
			   case 'n':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t\t GOODBYE";
			   	break;
			   case 'N':
			   	cout<<"\n\n\t\t\tshutting down in 5  seconds\r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 4  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 3  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 2  seconds    \r";
			   	Sleep(1000);
			   	cout<<"\t\t\tshutting down in 1   second    \r";
			   	Sleep(1000);
			   	cout<<"\t\t....................................";
			   	cout<<"\n\t\t\t GOODBYE";
			   	break;
			default:
				 SetConsoleTextAttribute( handle,  12);
				   	cout<<"please enter a valid Input\n";
				   	 SetConsoleTextAttribute( handle,  15);
				   	goto labelr;
				   	break;
				   }
				   	
				  }	}
		
				  
		} 	 




//This function calculates the number of days passed from some start point year
int calcDaysSoFar( int year, int month)
{
    int days;

    //calculates basic number of days passed 
    days = (year - firstYear) * 365;
    days += dayOffset;
    days += daysPassed[month-1];
    
    //add on the extra leapdays for past years
    for (int count = firstLeapYear; count < year ; count +=4)
    {
        if (isLeapYear(count) )
        {
            days++;
        }
    }

    //add leapday for this year if requested  month is greater than  Feb  
    if( month > 2 && isLeapYear(year) )
    {
        days++;
    }

    return days;

}


//This function checks whether a particular year is a leap year
bool isLeapYear( int year)
{
    return (!(year%4)&&(year%100))||!(year%400);
}


//Prints Month and Year
//followed by the day headings
//followed by the numbers
void printCalendar(int month, int year, int firstDay)
{
    string dayHeader = string("Sun ") + char(186) + "Mon " + char(186) + "Tue " + char(186) +
        "Wed " + char(186) + "Thu " + char(186) + "Fri " + char(186) + "Sat ";
    
    int innerWidth = dayHeader.length();
    stringstream sstream; //for converting the year to a string.
    string tempStr;

    cout << '\n';
    printGridTop(innerWidth);
    
    //print the month/year line
    sstream << year;
    tempStr = string(" ") + months[month-1] + string("     ") + sstream.str();
    cout << char(186);
    cout << tempStr;
    repeatChar(' ', innerWidth - tempStr.length());
    cout << char (186);
    
    //Draw a dividing line
    cout << '\n';
    cout << char(204);
    for (int count =0; count < 7; count ++)
    {
        repeatChar(char(205),4);
        if( count != 6)
        {
            cout << char(203);
        }
    }
    cout << char(185);
    cout << '\n';
    
    
    //print the day header line
    cout << char(186);
    cout << dayHeader;
    //cout << "Sun " << "Mon " << "Tue " << "Wed " << "Thu " << "Fri " << "Sat ";//<< '\n';
    cout << char(186) << '\n';
    
    drawDivider(innerWidth); //draw a dividing horizontal line
    
    int count,offset;
    offset= 1 - firstDay;
    
    count = daysInMonth[month-1]; //get the number of days in this month

    //adjust if dealing with February and year is leap year
    if(isLeapYear(year) && (month==2) )
    {
        count++;
    }

    //loop to fill in rows
    int dayNum;
    for (int x = offset; x <= count; x +=7)
    {

        cout << char(186);
        for(dayNum= x; (dayNum < x+7) /*&& (column <= count)*/; dayNum++)
        {
            if ( dayNum <=0  || dayNum > count)
            {
                cout << setw(4) << left << setprecision(3) << "    " << char(186);; 
            }
            else
            {
                cout << setw(4) << left << setprecision(3) << setfill(' ') << dayNum << char(186);
            }

        }
        cout << '\n';
        if(dayNum <= count)
        {
            //draw a divider line after each row except the last
            drawDivider(innerWidth);
        }
    }

    printGridBottom(innerWidth);

}


//draws the top of the drid
void printGridTop(int innerWidth)
{
    cout << char (201) ;
    repeatChar((char)205,innerWidth);    
    cout << char (187);
    cout << '\n';

}

//this just repeats a char a nomber of times
void repeatChar(char ch, int numChar)
{
    string aStr(numChar, ch);
    cout << aStr;
}

//draws a line between rows
void drawDivider(int innerWidth)
{
    cout << char(204);
    for (int count =0; count < 7; count ++)
    {
        repeatChar(char(205),4);
        if( count != 6)
        {
            cout << char(206);
        }
    }
    cout << char(185);
    cout << '\n';
}

//draws the bottom line of the grid
void printGridBottom(int innerWidth)
{
    cout << char(200);
    for (int count =0; count < 7; count ++)
    {
        repeatChar(char(205),4);
        if( count != 6)
        {
            cout << char(202);
        }
    }
    cout << char(188);
    cout << '\n';
}

