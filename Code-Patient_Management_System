#include<fstream>
#include<iostream>
#include <sstream>
#include <string>
#include<iomanip>
#include<random>

using namespace std;

long long int chkNum(string a);    //function declarartion
string chkDate();                  //function declarartion
template<typename T>               //template creation
T chkName(T a);                    //Function template



class patient                      //Base Class
{
public:
    int bp,weight;
    string phnum,temp,name,dob,add;
    patient()                     //Constructor
    {
        cout<<"\nEnter Patient Name :";
        getline(cin,temp);
        name=chkName(temp);
        cout<<"Enter Patient's Date of Birth "<<endl;
        dob=chkDate();
        //cin.ignore();
        //getline(cin,dob);
        phone:
            {
              cout<<"Enter Phone Number :";
              cin>>phnum;

            }
        try                              //Exception handling
        {
           if(phnum.size()!=10)
              throw (0);

        }
        catch(...)
        {
            cout<<"Entered Number is Invalid"<<endl;
            goto phone;
        }
        weights:
        {
        cout<<"Enter Weight(Whole number) :";
        cin>>temp;
        weight=chkNum(temp);
        }
        try
        {
        if(weight<30 || weight>200)
            throw 0;
        }
        catch(...)
        {
            cerr<<"Invalid Weight"<<endl;
            goto weights;
        }
        bps:
            {
            cout<<"Enter BP level :";
            cin>>temp;
            bp=chkNum(temp);
            }
        try
        {
        if(bp<75 || bp>220)
                throw 0;
        }
        catch(...)
        {
            cerr<<"Invalid BP level"<<endl;
            goto bps;
        }
        cout<<"Enter the Address (in a single line) :";
        cin.ignore();
        getline(cin,add);

        //cout<<name<<" "<<dob<<" "<<phnum<<" "<<weight<<" "<<bp<<" "<<add;

    }
    patient (int x)
    {
          //To avoid calling the Constructor when Derived class object Created
    }
    virtual void display()                      //VIRTUAL FUNCTION
        {

            cout<<"************************************************************************************************************************";
            cout<<"\n\tDETAILS OF THE PATIENT"<<endl;
            cout<<"\nName: "<<name<<endl;
            cout<<"Date of Birth: "<<dob<<endl;
            cout<<"Phone Number: "<<phnum<<endl;
            cout<<"Weight: "<<weight<<endl;
            cout<<"BP level: "<<bp<<endl;
            cout<<"Address: "<<add<<endl;
        }
        friend int dept(patient p);        //Friend Function

};







class outpatient: public patient          //Derived Class of Patient  (Hierarchical Inheritance )
{
public:
    string temp,appodate,refdoc,timeslot;
    int tok;
    outpatient():patient(0)               //This will call the Dummy constructor in the Base class
    {
        //Getting input form the Inpatient
        cout<<"\nFill the following Details asked below";
        cout<<"\nEnter Appointment Date"<<endl;
        appodate=chkDate();
        cout<<"Enter the Token number given by Nurse:";
        cin>>temp;
        tok=chkNum(temp);
        cout<<"Enter the Reference Doctor name(if any):";
        cin.ignore();
        getline(cin,temp);
        refdoc=chkName(temp);
        cout<<"Enter the Appointment Time Slot:";
        getline(cin,timeslot);
        cout<<"\n\tDETAILS OF THE OUTPATIENT ARE COLLECTED"<<endl;
    }
    void display()
    {
        cout<<"\nAppointment Date: "<<appodate<<endl;
        cout<<"Token Number: "<<tok<<endl;
        cout<<"Reference Doctor: "<<refdoc<<endl;
        cout<<"Appointment Time Slot: "<<timeslot<<endl;

    }

};






class inpatient:public patient                   //Derived Class of Patient
{
public:
    string adddate,attname,refdoc,temp;
    int wardno;
    inpatient():patient(0)                      //This will call the Dummy constructor in the Base class
    {
        //Getting input form the Outpatient
        cout<<"\nFill the following Details asked below";
        cout<<"\nEnter Admission Date"<<endl;
        adddate=chkDate();
        cout<<"Enter Ward Number alloted for you:";
        cin>>temp;
        wardno=chkNum(temp);
        cout<<"Enter Attender Name:";
        cin.ignore();
        getline(cin,temp);
        attname=chkName(temp);
        cout<<"Enter the Reference Doctor name(if any):";
        getline(cin,temp);
        refdoc=chkName(temp);
        cout<<"\n\tDETAILS OF THE INPATINET ARE COLLECTED"<<endl;

    }
    void display()
    {
        cout<<"\nAdmission Date: "<<adddate<<endl;
        cout<<"Ward Number: "<<wardno<<endl;
        cout<<"Attender Name: "<<attname<<endl;
        cout<<"Reference Doctor: "<<refdoc<<endl;
        //cout<<"************************************************************************************************************************";
    }

};

int dept(patient p)                 //Friend function
   {
       int choice;
       string temp;
       goto check;
       check:
       {
       cout<<"\n\n\tSELECT A PARTICULAR SPECIALIZATION ";
       cout<<"\n1.Cardiology"<<endl;
       cout<<"2.Neurology"<<endl;
       cout<<"3.Oncology"<<endl;
       cout<<"4.Radiology"<<endl;
       cout<<"5.Nephrology"<<endl;
       cout<<"6.General Medicine"<<endl;
       cout<<"Enter your choice :";
       cin>>temp;
       choice=chkNum(temp);
       switch(choice)
       {
       case 1 ... 6 :
               break;
       default:
            cout<<"Sorry :( You have made a Wrong choice!!! Please select again";
            goto check;

       }
       }
        return choice;

   }

string doctorlist(int x)
   {
        int var=x,slot[3];
        string doc[3];
        ifstream file;                                // ifstream for reading
        switch(var)
        {
        case 1:
            file.open("Cardiology.txt");             //Opening Corresponding Files
            break;
        case 2:
            file.open("Neurology.txt");
            break;
        case 3:
            file.open("Oncology.txt");
            break;
        case 4:
            file.open("Radiology.txt");
            break;
        case 5:
            file.open("Nephrology.txt");
            break;
        case 6:
            file.open("General medicine.txt");
            break;
        }
    if (file.is_open())                          //Checking that File is not Empty
        {
            string doctorr;
            int i=0;
            cout<<endl;
            while(file>>doc[i]>>slot[i])
            {
                cout<<i+1<<" "<<doc[i]<<endl;
                i++;
            }


       file.close();                            // Close the file when done
       }
    else
       {
           cout << "Unable to open file\n";      //Error Message
           exit(0);
           return "Error";
       }


       int choice;
       string incharge,temp;
       goto check;
       check:
       {

        do{
            cout<<"\nChoose your Preferred Doctor(1/2/3):";
            cin>>temp;
            choice=chkNum(temp);
        }while(choice!=1 && choice !=2 && choice !=3);
            if(choice==1)
            {
                if(slot[0]!=0)
                {
                    cout<<"\n\tAPPOINTMENT BOOKED SUCCESSFULLY"<<endl;
                    cout<<"\t   CONSULTED WITH THE DOCTOR"<<endl;
                    slot[0]--;
                    incharge=doc[0];
                }
                else{
                cout<<"\nThe Doctor you preferred is full of his/her slots\nChoose an alternate Doctor";
                goto check;
            }
            }
            else if(choice==2)
            {
                if(slot[1]!=0)
                {
                    cout<<"\n\tAPPOINTMENT BOOKED SUCCESSFULLY"<<endl;
                    cout<<"\t   CONSULTED WITH THE DOCTOR"<<endl;
                    slot[1]--;
                    incharge=doc[1];
                }
                else{
                cout<<"\nThe Doctor you preferred is full of his/her slots\nChoose an alternate Doctor";
                goto check;
            }
            }
            else if(choice==3)
            {
                if(slot[2]!=0)
                {
                    cout<<"\n\tAPPOINTMENT BOOKED SUCCESSFULLY"<<endl;
                    cout<<"\t   CONSULTED WITH THE DOCTOR"<<endl;
                    slot[2]--;
                    incharge=doc[2];
                }
                else{
                cout<<"\nThe Doctor you preferred is full of his/her slots\nChoose an alternate Doctor"<<endl;
                goto check;
            }
            }

       }

       cout<<"\nCurrent Status of Slots"<<endl;
       for(int i=0;i<3;i++)
       {
           cout<<doc[i]<<" "<<slot[i]<<endl;

        }


        return incharge;
}

class Billing                                           //Another Base Class
{
public:
    int billamt=0,lower,upper;
    string ins,temp;
    Billing()
    {
        //To avoid unnecessary calling of Constructor
    }
    Billing(int type)
    {
      random_device rd;                                    //Create a random device
      mt19937 gen(rd());                                   //Mersenne Twister random number generator
      if(type==1)                                      //Outpatient-->pass 1 with constructor
      {
          lower=1000,upper=5000;                          //Declaring th range
          uniform_int_distribution<> distr(lower,upper);  // Define the distribution
          billamt=distr(gen);
      }
      else                                             //Inpatient-->pass 2 with constructor
      {
          int days;
          lower=20000,upper=30000;
          uniform_int_distribution<> distr(lower,upper);
          billamt=distr(gen);
          cout<<"\nHow many days was Patient Admitted ? :";
          cin>>temp;
          days=chkNum(temp);
          billamt=billamt*days;
          cout<<"Do you have any Insurance ?(yes/no) :";
          cin.ignore();
          getline(cin,temp);
          ins=chkName(temp);
          //setBill(billamt);
      }
    }
    void payment()
    {
        string temp;
        int amt;
        cout<<"\nTotal Bill amount(including Treatment,Medications,Doctor Fee,Lab tests) - Rs "<<billamt<<"/-";
        label:
        {
           cout<<"\nEnter the Amount you are paying now (At least 50% ) - Rs";
           cin>>temp;
           amt=chkNum(temp);
        }
        try{
            if(amt<(50*billamt)/100)
                throw 0;
            else if(amt>billamt)
                throw 'c';
            billamt-=amt;
        }
        catch(int x)
        {
            cerr<<"\nAmount paid is less than 50% of the Total Bill Amount";
            goto label;
        }
        catch(char x)
        {
            cerr<<"\nAmount paid is gretaer than the Total Bill Amount Check Properly";
            goto label;
        }

        cout<<"\nDue Amount to be paid within today- Rs"<<billamt<<endl;
    }

    void setBill(int x)
    {
        billamt=x;
    }
    void getBill()
    {
        cout<<"\nTotal Bill amount(including Treatment,Medications,Doctor Fee,Lab tests) - Rs "<<billamt<<"/-";
    }
};

class Insurance:public Billing                //Derived class of Billing
{
public:
    int bill,elig;
    string temp;
   Insurance(int x)
  {
    cout<<"\nTotal Bill amount(including Treatment,Medications,Doctor Fee,Lab tests) - Rs "<<x<<"/-";
    cout<<"\nEnter the Total Sum assured of your Insurance Policy :";
    cin>>temp;
    elig=(chkNum(temp)*80)/100;
    cout<<"Eligible Amount is 80% of your Assured Sum :"<<elig<<endl;
    cout<<"Enter the Amount Approved by the Insurance company for your Bill :";
    amt:
    {
        cin>>temp;
        if(chkNum(temp)>elig)
            {
                cout<<"\nEntered Amount is greater than your Eligible Amount!!! Check Correctly\nEnter the Amount Approved by the Insurance company for your Bill :";
                goto amt;
            }
        else if(chkNum(temp)>x)
            {
                cout<<"\nEntered Amount is greater than your Bill Amount!!! Check Correctly ";
                goto amt;
            }
        else
        {
            bill=x-chkNum(temp);
            cout<<"\nThe Approved amount is deducted from your Bill"<<endl;
        }

    }
  }
};
template <typename T>
T chkName(T a)
{
   string s=a;
   int flag=1;
    for(int i=0;i<a.size();i++)
    {
        if(isalpha(a[i])==0 && a[i]!=' ' &&a[i]!='.')
        {
          flag=0;
          cout<<"Only Alphabets\nEnter name :" ;
          getline(cin,s);
          return (chkName(s));
        }

    }
    if(flag==1)
        return s;
}

long long int chkNum(string a)
{
   string s=a;

    for(int i=0;i<s.size();i++)
    {
        if(!isdigit(s[i]))
        {
          cout<<"Only Numbers\nEnter correct number :" ;
          cin>>s;
          return chkNum(s);
          break;
        }

    }
    //cout<<stoi(s);
    return stoi(s);
}

string chkDate()
{
    string temp,date="";
   // goto val;
    val1:
    {
    do
    {
        temp="";
        cout<<"Date:";
        cin>>temp;
    }while(temp.size()>2 );
    int chk=chkNum(temp);
    if(chk>0 && chk<=31)
         ;
    else
    {
        cerr<<"Invalid Date"<<endl;
        goto val1;
    }

    }
    date+=to_string(chkNum(temp));
    date+='-';
    val2:
    {
    do
    {
        temp="";
        cout<<"Month:";
        cin>>temp;
    }while(temp.size()>2);
    int chk=chkNum(temp);
     if(chk>0 && chk<=12)
         ;
    else
    {
        cerr<<"Invalid Month"<<endl;
        goto val2;
    }
   }
    date+=to_string(chkNum(temp));
    date+='-';
    val3:
    {
    do
    {
        temp="";
        cout<<"Year:";
        cin>>temp;
    }while(temp.size()!=4);
    int chk=chkNum(temp);
   if(chk>1924 && chk<=2024)
         ;
    else
    {
        cerr<<"Invalid Year"<<endl;
        goto val3;
    }
    }
    date+=to_string(chkNum(temp));
    return date;

}



int main()
{
    cout<<"\n\t\t\t\t\t\t\t\t  PATIENT MANAGEMENT SYSTEM"<<endl;
    cout<<"\n\t\t\t\t\t\t\t\t\t  WELCOME     \n\t\t\t\t\t\t\t\t\tBelieve in us\n\t\t\t\t\t\t\t\tWe are here to hear and heal"<<endl;
    int choice,department;
    string incharge,temp;
    patient p;                                //Class Object
    patient *ptr;                             //Pointer object
    department=dept(p);
    incharge=doctorlist(department);
    goto check;
    check:
    {
    cout<<"\nUpon Doctor's Consultation Are you an\n1.Outpatient\n2.Inpatient\nEnter(1/2) :";
    cin>>temp;
    choice=chkNum(temp);
    if(choice==1)
        {
            outpatient o;
            ptr=&o;
            Billing b(1);                        //Billing class object with a Parameter
            p.display();
            ptr->display();
            cout<<"\nINCHARGE DOCTOR FOR THIS PATIENT IS "<<incharge<<endl;
            cout<<"************************************************************************************************************************"<<endl;
            cout<<"\n\tPAYMENT DETAILS"<<endl;
            b.payment();
        }
    else if(choice==2)
        {
            inpatient i;
            ptr=&i;
            Billing b(2);                       //Billing class object with a Parameter
            p.display();
            ptr->display();
            cout<<"\nINCHARGE DOCTOR FOR THIS PATIENT IS "<<incharge<<endl;
            cout<<"************************************************************************************************************************"<<endl;
            cout<<"\n\tPAYMENT DETAILS"<<endl;
            if(b.ins=="yes" || b.ins=="YES" || b.ins=="Yes")
            {
                Insurance obj(b.billamt);
                b.setBill(obj.bill);
            }
            b.payment();
        }
    else
    {
        cout<<"\nInvalid Choice Try Again"<<endl;
        goto check;
    }
    }

    cout<<"************************************************************************************************************************"<<endl;

}
