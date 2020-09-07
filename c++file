#include<iostream.h>
#include<conio.h>
#include<process.h>
#include<stdio.h>
#include<string.h>
#include<ctype.h>
#include<dos.h>
#include<fstream.h>

void preface()
//a function to show the preface
{
	clrscr();
	cout<<"\nThis is programme on school management system.\n";
	cout<<"\nThis was done by PROGRAMMER-ABHIJEET\n";
	cout<<"\nGUIDED BY HIS TEACHER GOVIND RAO\n\n"; 
	
	
	getch();
}
void head()
//a function to show the heading
{
	clrscr();
	for(int i=0;i<80;i++)
	cout<<"”_”";
	cout<<"”\n\t\t --- ------ School, Management System\n”";
	for(i=0;i<80;i++)
	cout<<"”_”";
	cout<<endl;
}
int list()
//a function to show the sub-menu
{
	int i;
	cout<<endl;
	cout<<"Press :\n\n";
	cout<<"\t1 -> Add data\n\n";
	cout<<"\t2 -> Edit data\n\n";
	cout<<"\t3 -> Show data\n\n";
	cout<<"\t4 -> Delete data\n\n";
	cout<<"\t5 -> Return to main screen\n\n\n-> ";
	cin>>i;
	return i;
}

void front();	//function declaration

class student
//a class to that contains necessary details of students
{
	public:
		long roll_no;
		char name[30];
		int adm_no,std;
		char excels_in[100];
};

void display(student s)
//a function to display details of a student
{
	cout<<"\nName : "<<s.name;
	cout<<"\n\nAdmission no. : "<<s.adm_no;
	cout<<"\n\nClass : "<<s.std;
	cout<<"\n\nRoll no. : "<<s.roll_no;
	cout<<"\n\nExcels in : "<<s.excels_in<<endl;
}

void s_input()
//a function to allow the input of new student's data to the system
{
	student s,t;
	ofstream file;
	file.open("data.dat", ios::out | ios::app | ios::binary);
	ifstream ifile;
	ifile.open("data.dat", ios::in | ios::binary);
	C:
	clrscr();
	cout<<"\nEnter the name of the student :\n\n-> ";
	gets(s.name);
	cout<<"\nEnter the admission no. :\n\n-> ";
	cin>>s.adm_no;
	ifile.read((char *)&t, sizeof(student));
	while(ifile)
	{
		if(t.adm_no==s.adm_no)
		{
			clrscr();
			cout<<"\nDuplicate admission no...\n";
			getch();
			goto C;
		}
		ifile.read((char *)&t, sizeof(student));
	}
	ifile.close();
	cout<<"\nEnter the class :\n\n-> ";
	cin>>s.std;
	cout<<"\nEnter the roll no. :\n\n-> ";
	cin>>s.roll_no;
	ifile.open("data.dat", ios::in | ios::binary);
	ifile.read((char *)&t, sizeof(student));
	while(ifile)
	{
		if(t.std==s.std&&t.roll_no==s.roll_no)
		{
			clrscr();
			cout<<"\nDuplicate roll no...\n";
			getch();
			goto C;
		}
		ifile.read((char *)&t, sizeof(student));
	}
	cout<<"\nEnter the field he/she excels in :\n\n-> ";
	gets(s.excels_in);
	file.write((char *)&s, sizeof(student));
	clrscr();
	display(s);
	cout<<"\n\nData added.";
	file.close();
	ifile.close();
	getch();
}

void s_edit()
//a function to edit the student's details
{
	clrscr();
	student s,t;
	fstream file;
	file.open("data.dat", ios::in | ios::out | ios::binary);
	cout<<"\nEnter the admission no. of the student :\n\n-> ";
	int n1,n;
	cin>>n1;
	int flag=0;
	clrscr();
	file.read((char *)&s, sizeof(student));
	while(file)
	{
		if(n1==s.adm_no)
		{
			display(s);
			B:
			cout<<"\n\nWhat is to be edited ?\n";
			cout<<"\nPress to change :\n";
			cout<<"\n\t1 -> Name\n";
			cout<<"\n\t2 -> Admission no.\n";
			cout<<"\n\t3 -> Class\n";
			cout<<"\n\t4 -> Roll no.\n";
			cout<<"\n\t5 -> Excels in\n\n-> ";
			cin>>n;
			switch(n)
			{
				case 1: cout<<"\nEnter the name :\n\n-> ";
				gets(s.name);
				break;
				case 2:
				H:
				cout<<"\nEnter the admission no. :\n\n-> ";
				cin>>s.adm_no;
				ifstream ifile("Data.dat", ios::in | ios::binary);
				ifile.read((char *)&t, sizeof(student));
				while(ifile)
				{
					if(t.adm_no==s.adm_no)
					{
						if(t.std!=s.std || t.roll_no!=s.roll_no)
						{
							clrscr();
							cout<<"\nDuplicate admission no...\n";
							getch();
							clrscr();
							goto H;
						}
					}
					ifile.read((char *)&t, sizeof(student));
				}
				ifile.close();
				break;
				case 3: cout<<"\nEnter the class :\n\n-> ";
				cin>>s.std;
				break;
				case 4:
				I:
				cout<<"\nEnter the roll no. :\n\n-> ";
				cin>>s.roll_no;
				ifstream infile("Data.dat", ios::in | ios::binary);
				infile.read((char *)&t, sizeof(student));
				while(infile)
				{
					if(t.roll_no==s.roll_no&&t.std==s.std)
					{
						if(t.adm_no!=s.adm_no)
						{
							clrscr();
							cout<<"\nDuplicate roll no...\n";
							getch();
							clrscr();
							goto I;
						}
					}
					infile.read((char *)&t, sizeof(student));
				}
				infile.close();
				break;
				case 5: cout<<"\nEnter in which he/she excels in :\n\n-> ";
				gets(s.excels_in);
				break;
				default: cout<<"\nIncorrect option selected..";
				goto B;
			}
			int pos;
			pos=(-1)*sizeof(student);
			file.seekp(pos,ios::cur);
			file.write((char *)&s, sizeof(student));
			flag=1;
			clrscr();
			display(s);
			cout<<"\n\nData updated.";
		}
		file.read((char *)&s, sizeof(student));
	}
	if(flag==0)
		cout<<"\nNo such data found..";
	file.close();
	getch();
}

void s_show()
//a function to show the desired students' details
{
	clrscr();
	student s;
	int flag=0;
	ifstream file;
	file.open("data.dat", ios::in | ios::binary);
	cout<<"\nPress :\n\n";
	cout<<"\t1 -> Single selection\n";
	cout<<"\n\t2 -> Class selection\n\n-> ";
	int i;
	cin>>i;
	int n;
	if(i==1)
	{
		cout<<"\nEnter the admission no. of the student :\n\n-> ";
		cin>>n;
		clrscr();
		file.read((char *)&s, sizeof(student));
		while(file)
		{
			if(n==s.adm_no)
			{
				display(s);
				flag=1;
			}
			file.read((char *)&s, sizeof(student));
		}
	}
	else if(i==2)
	{
		cout<<"\nEnter the class :\n\n-> ";
		cin>>n;
		clrscr();
		int j=1;
		file.read((char *)&s, sizeof(student));
		gotoxy(1,2);
		cout<<"Name";
		gotoxy(30,2);
		cout<<"Admn no.";
		gotoxy(45,2);
		cout<<"Roll no.";
		gotoxy(58,2);
		cout<<"Excels in\n";
		for(int k=0; k<80; k++)
			cout<<"-";
		while(file)
		{
			if(n==s.std)
			{
				j+=2;
				gotoxy(1,j+2);
				cout<<s.name;
				gotoxy(30,j+2);
				cout<<s.adm_no;
				gotoxy(45,j+2);
				cout<<s.roll_no;
				gotoxy(58,j+2);
				cout<<s.excels_in;
				cout<<endl;
				flag+=1;
			}
			file.read((char *)&s, sizeof(student));
		}
		if(flag!=0)
			cout<<"\n\nTotal strength of class "<<n<<" : "<<flag;
	}
	if(flag==0)
		cout<<"\nNo such data found..";
	file.close();
	getch();
}

void s_delete()
//a function to delete a student's data
{
	clrscr();
	fstream del,add;
	student s;
	int flag=0;
	cout<<"\nEnter the admission no. :\n\n-> ";
	int n;
	cin>>n;
	del.open("data.dat", ios::in | ios::binary);
	add.open("tempdata.dat", ios::out | ios::binary | ios::trunc);
	clrscr();
	del.read((char *)&s, sizeof(student));
	while(del)
	{
		if(s.adm_no!=n)
			add.write((char *)&s, sizeof(student));
		else
		{
			display(s);
			flag=1;
			cout<<"\n\nDo you really want to delete the data ? (Yes/No)\n\n-> ";
			char ch[3];
			gets(ch);
			for(int j=0; ch[j]!='\0'; j++)
				ch[j]=toupper(ch[j]);
			if(!strcmp(ch,"YES"))
			{}
			else
			{
				remove("tempdata.dat");
				cout<<"\n\nData not deleted.";
				goto D;
			}
		}
		del.read((char *)&s, sizeof(student));
	}
	if(flag==0)
		cout<<"\nNo such data found..";
	else
	{
		remove("data.dat");
		rename("tempdata.dat","data.dat");
		cout<<"\n\nData deleted.";
	}
	D:
	del.close();
	add.close();
	getch();
}

void s_main()
//a function to link the students' file operations with the sub-menu
{
	int opt=0;
	while(1)
	{
		A:
		head();
		cout<<"\nStudents' File Management\n\n";
		opt=list();
		switch(opt)
		{
			case 1: s_input();
			break;
			case 2: s_edit();
			break;
			case 3: s_show();
			break;
			case 4: s_delete();
			break;
			case 5: front();
			break;
			default: cout<<"\nIncorrect option selected..\n";
			getch();
			goto A;
		}
	}
}

class staff
{
	public:
		long id;
		char name[30];
		float HRA,DA,PF,Basic;
		char department[20];
};

void sf_display(staff s)
//a class to that contains necessary details of staffs
{
	cout<<"\nName : "<<s.name;
	cout<<"\n\nStaff ID : "<<s.id;
	cout<<"\n\nHRA : "<<s.HRA;
	cout<<"\n\nDA : "<<s.DA;
	cout<<"\n\nPF : "<<s.PF;
	cout<<"\n\nBasic Salary : "<<s.Basic;
	cout<<"\n\nDepartment : "<<s.department<<endl;
}

void sf_input()
//a function to allow the input of new staff's data to the system
{
	staff s,t;
	ofstream file;
	file.open("data1.dat", ios::out | ios::app | ios::binary);
	ifstream ifile;
	ifile.open("data1.dat", ios::in | ios::binary);
	M:
	clrscr();
	cout<<"\nEnter the name of the staff :\n\n-> ";
	gets(s.name);
	cout<<"\nEnter the staff ID :\n\n-> ";
	cin>>s.id;
	ifile.read((char *)&t, sizeof(staff));
	while(ifile)
	{
		if(t.id==s.id)
		{
			clrscr();
			cout<<"\nDuplicate staff ID...\n";
			getch();
			goto M;
		}
		ifile.read((char *)&t, sizeof(staff));
	}
	ifile.close();
	cout<<"\nEnter the HRA :\n\n-> ";
	cin>>s.HRA;
	cout<<"\nEnter the DA :\n\n-> ";
	cin>>s.DA;
	cout<<"\nEnter the PF :\n\n-> ";
	cin>>s.PF;
	cout<<"\nEnter the Basic salary :\n\n-> ";
	cin>>s.Basic;
	cout<<"\nEnter the department :\n\n-> ";
	gets(s.department);
	file.write((char *)&s, sizeof(staff));
	clrscr();
	sf_display(s);
	cout<<"\n\nData added.";
	file.close();
	ifile.close();
	getch();
}

void sf_edit()
//a function to edit the staff's details
{
	clrscr();
	staff s,t;
	fstream file;
	file.open("data1.dat", ios::in | ios::out | ios::binary);
	cout<<"\nEnter the ID of the staff :\n\n-> ";
	int n1,n;
	cin>>n1;
	int flag=0;
	clrscr();
	file.read((char *)&s, sizeof(staff));
	while(file)
	{
		if(n1==s.id)
		{
			sf_display(s);
			N:
			cout<<"\n\nWhat is to be edited ?\n";
			cout<<"\nPress to change :\n";
			cout<<"\n\t1 -> Name\n";
			cout<<"\n\t2 -> Staff ID\n";
			cout<<"\n\t3 -> HRA\n";
			cout<<"\n\t4 -> DA\n";
			cout<<"\n\t5 -> PF\n";
			cout<<"\n\t6 -> Basic\n";
			cout<<"\n\t7 -> Department\n\n-> ";
			cin>>n;
			switch(n)
			{
				case 1: cout<<"\nEnter the name :\n\n-> ";
				gets(s.name);
				break;
				case 2:
				J:
				cout<<"\nEnter the staff ID :\n\n-> ";
				cin>>s.id;
				ifstream ifile("Data1.dat", ios::in | ios::binary);
				ifile.read((char *)&t, sizeof(staff));
				while(ifile)
				{
					if(t.id==s.id)
					{
						if(strcmp(t.name,s.name))
						{
							clrscr();
							cout<<"\nDuplicate staff ID...\n";
							getch();
							clrscr();
							goto J;
						}
					}
					ifile.read((char *)&t, sizeof(staff));
				}
				ifile.close();
				break;
				case 3: cout<<"\nEnter the HRA :\n\n-> ";
				cin>>s.HRA;
				break;
				case 4: cout<<"\nEnter the DA :\n\n-> ";
				cin>>s.DA;
				break;
				case 5: cout<<"\nEnter the PF :\n\n-> ";
				cin>>s.PF;
				break;
				case 6: cout<<"\nEnter the Basic salary :\n\n-> ";
				cin>>s.Basic;
				break;
				case 7: cout<<"\nEnter the department :\n\n-> ";
				gets(s.department);
				break;
				default: cout<<"\nIncorrect option selected..";
				goto N;
			}
			int pos;
			pos=(-1)*sizeof(staff);
			file.seekp(pos,ios::cur);
			file.write((char *)&s, sizeof(staff));
			flag=1;
			clrscr();
			sf_display(s);
			cout<<"\n\nData updated.";
		}
		file.read((char *)&s, sizeof(staff));
	}
	if(flag==0)
		cout<<"\nNo such data found..";
	file.close();
	getch();
}

void sf_show()
//a function to show the desired staffs' details
{
	clrscr();
	staff s;
	int flag=0;
	ifstream file;
	file.open("data1.dat", ios::in | ios::binary);
	cout<<"\nPress :\n\n";
	cout<<"\t1 -> Single selection\n";
	cout<<"\n\t2 -> Department selection\n\n-> ";
	int i;
	cin>>i;
	if(i==1)
	{
		cout<<"\nEnter the ID of the staff :\n\n-> ";
		int n;
		cin>>n;
		clrscr();
		file.read((char *)&s, sizeof(staff));
		while(file)
		{
			if(n==s.id)
			{
				sf_display(s);
				flag=1;
			}
			file.read((char *)&s, sizeof(staff));
		}
	}
	else if(i==2)
	{
		cout<<"\nEnter the department :\n\n-> ";
		char n[20],n1[20];
		gets(n);
		for(int j=0; n[j]!='\0'; j++)
		{
			if(isalpha(n[j]))
			{
				n[j]=toupper(n[j]);
			}
		}
		clrscr();
		file.read((char *)&s, sizeof(staff));
		j=1;
		gotoxy(1,2);
		cout<<"Name";
		gotoxy(30,2);
		cout<<"Staff ID";
		gotoxy(42,2);
		cout<<"HRA";
		gotoxy(50,2);
		cout<<"DA";
		gotoxy(58,2);
		cout<<"PF";
		gotoxy(66,2);
		cout<<"Basic\n";
		for(int k=0; k<80; k++)
			cout<<"-";
		while(file)
		{
			strcpy(n1,s.department);
			for(int k=0; n1[k]!='\0'; k++)
			{
				if(isalpha(n1[k]))
				{
					n1[k]=toupper(n1[k]);
				}
			}
			if(!strcmp(n,n1))
			{
				j+=2;
				gotoxy(1,j+2);
				cout<<s.name;
				gotoxy(30,j+2);
				cout<<s.id;
				gotoxy(42,j+2);
				cout<<s.HRA;
				gotoxy(50,j+2);
				cout<<s.DA;
				gotoxy(58,j+2);
				cout<<s.PF;
				gotoxy(66,j+2);
				cout<<s.Basic;
				cout<<endl;
				flag+=1;
			}
			file.read((char *)&s, sizeof(staff));
		}
		if(flag!=0)
			cout<<"\n\nTotal staffs in department "<<n<<" : "<<flag;
	}
	if(flag==0)
		cout<<"\nNo such data found..";
	file.close();
	getch();
}

void sf_delete()
//a function to delete a staff's data
{
	clrscr();
	fstream del,add;
	staff s;
	int flag=0;
	cout<<"\nEnter the staff ID :\n\n-> ";
	int n;
	cin>>n;
	del.open("data1.dat", ios::in | ios::binary);
	add.open("tempdata.dat", ios::out | ios::binary | ios::trunc);
	clrscr();
	del.read((char *)&s, sizeof(staff));
	while(del)
	{
		if(s.id!=n)
			add.write((char *)&s, sizeof(staff));
		else
		{
			sf_display(s);
			flag=1;
			cout<<"\n\nDo you really want to delete the data ? (Yes/No)\n\n-> ";
			char ch[3];
			gets(ch);
			for(int k=0; k<3; k++)
				ch[k]=toupper(ch[k]);
			if(!strcmp(ch,"YES"))
			{}
			else
			{
				remove("tempdata.dat");
				cout<<"\n\nData not deleted.";
				goto O;
			}
		}
		del.read((char *)&s, sizeof(staff));
	}
	if(flag==0)
		cout<<"\nNo such data found..";
	else
	{
		remove("data1.dat");
		rename("tempdata.dat","data1.dat");
		cout<<"\n\nData deleted.";
	}
	O:
	del.close();
	add.close();
	getch();
}

void sf_main()
//a function to link the staffs' file operations with the sub-menu
{
	int opt=0;
	while(1)
	{
		P:
		head();
		cout<<"\nStaffs' File Management\n\n";
		opt=list();
		switch(opt)
		{
			case 1: sf_input();
			break;
			case 2: sf_edit();
			break;
			case 3: sf_show();
			break;
			case 4: sf_delete();
			break;
			case 5: front();
			break;
			default: cout<<"\nIncorrect option selected..\n";
			getch();
			goto P;
		}
	}
}

void front()
//a function that displays main menu and also displays exit dialog
{
	clrscr();
	Z:
	head();
	cout<<"\n\nPress :\n";
	cout<<"\n\t1 -> To open staffs' management file\n";
	cout<<"\n\t2 -> To open sudents' management file\n";
	cout<<"\n\t3 -> To exit\n";
	int n;
	cout<<"\n\n-> ";
	cin>>n;
	switch(n)
	{
		case 1: sf_main();
		break;
		case 2: s_main();
		break;
		case 3: delay(300);		//to delay for 300 milliseconds
		for(int i=0; i<3; i++)
		{
			clrscr();
			cout<<"\nThank You!\n";
			cout<<"\nSystem is closing";
			for(int j=0; j<3; j++)
			{
				delay(600);
				cout<<".";
				delay(600);
			}
		}
		delay(300);
		exit(0);
		break;
		default: cout<<"\nIncorrect option selected..\n";
		goto Z;
	}
	getch();
}

void main()
{
	preface();
	delay(300);
	for(int i=0; i<3; i++)
	{
		clrscr();
		cout<<"\nWelcome!\n";
		cout<<"\nSystem is loading";
		for(int j=0; j<3; j++)
		{
			delay(600);
			cout<<".";
			delay(600);
		}
	}
	delay(300);
	front();
}
