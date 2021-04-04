#include <iostream>
#include <string>
#include <ctype.h>
#include <Windows.h>
#include <locale.h>
using namespace std;

int main()
{   
	setlocale(LC_ALL,".866");
    string input;
	do	{
		cout<<"Input string, empty string close programm:"<<endl;
		getline(cin,input);
		int l=input.length();
		for (int i = 0;i<l;i++)
			input[i] = tolower(input[i]);
		string output(l,'0');
		int n = 0;
	    for (int i = 0;i<l;i++)
			if (output[i]!=')')
			{
			    n = 0;
		        for(int j = i+1;j<l;j++)
	                if (input[i] == input[j])
					{
						output[j] = ')';
					    n+=1;
				    }
			    if(n != 0)
		            output[i] = ')';
	            else
	             output[i] = '('; 
	        }
		cout<<"Output:"<<endl;
	    cout<<output<<endl;
	}	while (input.length() != 0);
}
