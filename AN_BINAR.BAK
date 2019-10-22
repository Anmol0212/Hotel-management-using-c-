# include"fstream.h"
# include "dos.h"
# include"conio.h"
# include"stdio.h"
# include"process.h"
	 int x=1;

     void display();
     void modify();
     void enter();
     void add();
     void search();





   class emp
{
   int code;
   char n[20];
   float sa;
   public:
   void input()
   {
    cout<<"\n\tDetails of employee..: "<<x<<endl<<endl;
    cout<<"\tEmp code::";
    cin>>code;
    cout<<"\tEmp name::";
    gets(n);
    cout<<"\tSALARY::";
    cin>>sa;
   x++;
   }

   int ret()
   {
   return code;
   }

    void displaying()
    {
    cout<<"\n\n\tYour record is...:";
    cout<<"\n\tEmp code:";
    cout<<code;
    cout<<"\n\tEmp name:";
    puts(n);
    cout<<"\tSALARY:";
    cout<<sa;
    }

    void nentry()
    {
    cout<<endl;
    cout<<"\n\tGive your details to be modify of an employee i.e....: ";
    cout<<"\n\tEmp code :";
    cin>>code;
    cout<<"\tEmp name :";
    gets(n);
    cout<<"\tSALARY :";
    cin>>sa;
    }
   void nadd()
   {
    cout<<endl;
    cout<<"\n\tGive your new record details of an  employee i.e....: ";
    cout<<"\n\tEmp code :";
    cin>>code;
    cout<<"\tEmp name :";
    gets(n);
    cout<<"\tSALARY :";
    cin>>sa;
   }


};

   emp e;
   void main()

   {
       clrscr();
       char z,g;

 s:
   cout<<"\n\t!!!WELCOME TO C++ CODING PRESENT BY ANMOL VARSHNEY!!!!";
   cout<<"\n\t\tPress E to enter new  records  of an employees";
   cout<<"\n\t\tPress M to modify the record of an employees";
   cout<<"\n\t\tPress A to add records of an employees";
   cout<<"\n\t\tPress D to display the records of an employees";
   cout<<"\n\t\tPress S to search the record of an employees";
   cout<<"\n\t\tPress X to exit";

   cout<<"\n\n\tENTER YOUR CHOICE::";
   cin>>z;
   switch(z)
   {
   case 'E': enter();break;
   case 'M': modify();break;
   case 'A': add();break;
   case 'D': display();break;
   case 'S': search();break;
   case 'X': exit(0);break;
   default : cout<<"\n\t1st see than enter";break;
   }
       cout<<"\n\n\t\t***:::TO CONTINUE PRESS Y:::***";
       cin>>g;
       if(g=='y'||g=='Y')
       {       clrscr();
       goto s;
       }
       else
       {
       exit(0);
       }
    }


void enter()
   {  clrscr();
      ofstream o;
      o.open("op.dat",ios::out|ios::binary);
      int n;
      cout<<"\n\tEnter how many records you wannt to enter::";
      cin>>n;
      for(int i=1;i<=n;i++)
    { e.input();
      o.write((char*)&e,sizeof(e));
    }
   o.close();
  }


void modify()
  {   int d;
 ifstream i;
 ofstream o;
  i.open("op.dat",ios::in|ios::binary);
  o.open("op2.dat",ios::out|ios::binary);
  cout<<"\n\n\tEnter the employee code for which you  want to do modify  :";
  cin>>d;
	  while(i.read((char*)&e,sizeof(e)))
	  {
	     if(e.ret()==d)
	     {
	      e.displaying();
	      e.nentry();
	     }
	      o.write((char*)&e,sizeof(e));
	  }

   i.close();
   o.close();
   remove("op.dat");
   rename("op2.dat","op.dat");





   }


      void display()
      {
	ifstream i;
	i.open("op.dat" ,ios::in|ios::binary);
	while(i.read((char*)&e,sizeof(e)))
	{

	e.displaying();
	getch();
	}

       i.close();
      }

   void add()

 {      ifstream i;
	ofstream o;
	int d;
	cout<<"Enter the code of an emp. after which your new record is to be given ...:";
	cin>>d;
      i.open("op.dat",ios::in|ios::binary);
      o.open("op2.dat",ios::out|ios::binary);


	while(i.read((char*)&e,sizeof(e)))
	  {   o.write((char*)&e,sizeof(e));
	     if(e.ret()==d)
	     { e.nadd();
	      o.write((char*)&e,sizeof(e));
	      }

	  }
   i.close();
   o.close();
   remove("op.dat");
   rename("op2.dat","op.dat");

	}

     void search()
     {       int f=0,d;
	cout<<"Enter the code of an emp. to be searched ...:";
	cin>>d;
	ifstream i;
	i.open("op.dat",ios::in|ios::binary);
	while(i.read((char*)&e,sizeof(e)))
	  {
	  if(e.ret()==d)
	     { f=1;
	     e.displaying();
	     }

	  }
	  if (f==0)
	  {
	  cout<<"!!!RECORD NOT FOUND!!!";
	  }
     i.close();
     }


