# Payroll-Management-System-with-Python-Tkinter
import random 
from tkinter import*
import time
import datetime

payroll= Tk()
payroll.geometry("1350x650+0+0")
payroll.title("Vinnie Payroll System")

def Exit():
    payroll.destroy()
def Reset():
    EmployeeName.set("")
    EmployeeAddress.set("")
    EmployerName.set("")
    cityWeighting .set("")
    OverTime.set("")
    GrossPay.set("")
    BasicSalary.set("")
    NetPay.set("")
    Tax.set("")
    Pension.set("")
    StudentLoan.set("")
    NIPayment.set("")
    Deductions.set("")
    PostCode.set("")
    Gender.set("")
    NICode.set("")
    NINumber.set("")
    TaxPeriod.set("")
    TaxablePay.set("")
    PensionablePay.set("")
    Deductions.set("")
    OtherPaymentsDue.set("")
    Paydate.set("")
    NINumber.set("")
    ReferenceNO.set("")

def PayRef() :
    Paydate.set(time.strftime("%d/%m/%y"))
    Refpay= random.randint(2000, 709467)
    Refpaid=("PR"+str (Refpay))
    ReferenceNO.set(Refpaid)

    NIpay= random.randint(2000, 709467)
    NIpaid=("NI"+str (Refpay))
    NINumber.set(NIpaid)
def PayPeriod() :
    i= datetime.datetime.now()
    TaxPeriod.set(i.month)

    NCode =random.randint(1200, 4467)
    CodeNI= ("NICode" +str(NCode))
    NICode.set(CodeNI)
def MonthlySalary():
    BS= float(BasicSalary.get())
    CW= float (cityWeighting.get())
    OT= float (OverTime.get())

    M_Tax= (BS+CW+OT)*0.3
    MMTax="$",str('%.2f'%(M_Tax))
    Tax.set(MMTax)

    M_Pension= (BS+CW+OT)*0.02
    MM_Pension="$",str('%.2f'%(M_Pension))
    Pension.set(MM_Pension)

    S_Loan= (BS+CW+OT)*0.012
    SS_Loan="$",str('%.2f'%(S_Loan))
    StudentLoan.set(SS_Loan)

    M_NIPay=(BS+CW+OT)*0.011
    MM_NIPay="$",str('%.2f'%(M_NIPay))
    NIPayment.set(MM_NIPay)

    M_Deductions=(M_Tax+M_Pension+S_Loan+M_NIPay)
    MM_Deductions= '$',str('%.2f' %(M_Deductions))
    Deductions.set(MM_Deductions)
    
    M_Gross= (BS+CW+OT)
    Gross_Pay ='$',str('%.2f' %(BS+CW+OT))
    GrossPay.set(Gross_Pay)

    M_NetPay=(M_Gross-M_Deductions)
    MM_NetPay= '$',str('%.2f' %(M_NetPay))
    NetPay.set(MM_NetPay)

    TaxablePay.set(MMTax)
    PensionablePay.set(MM_Pension)
    OtherPaymentsDue.set("0.00")
    

EmployeeName =StringVar()
EmployeeAddress =StringVar()
ReferenceNO =StringVar()
EmployerName =StringVar()
cityWeighting =StringVar()
OverTime =StringVar()
GrossPay =StringVar()
BasicSalary =StringVar()
NetPay =StringVar()
Tax =StringVar()
Pension =StringVar()
StudentLoan =StringVar()
NIPayment =StringVar()
Deductions =StringVar()
PostCode =StringVar()
Gender =StringVar()
NICode =StringVar()
NINumber =StringVar()
TaxPeriod =StringVar()
TaxablePay =StringVar()
PensionablePay =StringVar()
Deductions =StringVar()
OtherPaymentsDue =StringVar()
Paydate =StringVar()


Tops=Frame(payroll,width=1350 ,height=50, bd=8 ,relief='raise' )
Tops.pack(side=TOP)
LF=Frame(payroll,width=700 ,height=650, bd=16 ,relief='raise' )
LF.pack(side=LEFT)
RF=Frame(payroll,width=600 ,height=650 ,bd=16 ,relief='raise')
RF.pack(side=RIGHT)


lblInfo= Label(Tops ,font=('arial',50,'bold'),text="Vinnie PayRoll System" ,fg='Steel Blue',bd=1)
lblInfo.grid(row=0,column=0)

LeftInsideLF=Frame(LF ,width=700 ,height=100, bd=8 ,relief='raise')
LeftInsideLF.pack(side=TOP)
LeftInsideLFLF=Frame(LF ,width=325 ,height=400, bd=8 ,relief='raise')
LeftInsideLFLF.pack(side=LEFT)
LeftInsideRLLF=Frame(LF ,width=325 ,height=400, bd=8 ,relief='raise')
LeftInsideRLLF.pack(side=RIGHT)

RightInsideLF=Frame(RF ,width=600 ,height=100, bd=8 ,relief='raise')
RightInsideLF.pack(side=TOP)
RightInsideLFLF=Frame(RF ,width=300,bd=8 ,relief='raise' )
RightInsideLFLF.pack(side=LEFT)
RightInsideRLLF=Frame(RF ,width=300 ,height=400,bd=8 ,relief='raise')
RightInsideRLLF.pack(side=RIGHT)
#================================Right Side================================================================================
lblEmployeeName= Label(LeftInsideLF ,font=('arial',12,'bold'),text="Employee Name" ,fg='Steel Blue',bd=10, anchor='w')
lblEmployeeName.grid(row=0,column=0)
txtEmployeeName= Entry(LeftInsideLF ,font=('arial',12,'bold'),bd=20,width=54, bg='Powder Blue', justify='left',textvariable=EmployeeName )
txtEmployeeName.grid(row=0,column=1)

lblEmployeeAddress= Label(LeftInsideLF ,font=('arial',12,'bold'),text="Employee Address" ,fg='Steel Blue',bd=10, anchor='w')
lblEmployeeAddress.grid(row=1,column=0)
txtEmployeeAddress= Entry(LeftInsideLF ,font=('arial',12,'bold'),bd=20,width=54,bg='Powder Blue',justify='left',textvariable=EmployeeAddress )
txtEmployeeAddress.grid(row=1,column=1)

lblReferenceNO= Label(LeftInsideLF ,font=('arial',12,'bold'),text="Reference No" ,fg='Steel Blue',bd=10, anchor='w')
lblReferenceNO.grid(row=2,column=0)
txtReferenceNO= Entry(LeftInsideLF ,font=('arial',12,'bold'),bd=20,width=54, bg='Powder Blue', justify='left',textvariable=ReferenceNO )
txtReferenceNO.grid(row=2,column=1)

lblEmployerName= Label(LeftInsideLF ,font=('arial',12,'bold'),text="Employer Name" ,fg='Steel Blue',bd=10, anchor='w')
lblEmployerName.grid(row=3,column=0)
txtEmployerName= Entry(LeftInsideLF ,font=('arial',12,'bold'),bd=20,width=54,bg='Powder Blue', justify='left',textvariable=EmployerName )
txtEmployerName.grid(row=3,column=1)

#==========================INSIDE LFLF=====================================================================================
lblcityWeighting= Label(LeftInsideLFLF ,font=('arial',12,'bold'),text="City Weighting" ,fg='Steel Blue',bd=10, anchor='w')
lblcityWeighting.grid(row=0,column=0)
txtcityWeighting= Entry(LeftInsideLFLF ,font=('arial',12,'bold'),bd=10,width=18, bg='Powder Blue', justify='left',textvariable=cityWeighting )
txtcityWeighting.grid(row=0,column=1)

lblBasicSalary= Label(LeftInsideLFLF ,font=('arial',12,'bold'),text="Basic Salary" ,fg='Steel Blue',bd=10, anchor='w')
lblBasicSalary.grid(row=1,column=0)
txtBasicSalary= Entry(LeftInsideLFLF ,font=('arial',12,'bold'),bd=10,width=18, bg='Powder Blue', justify='left',textvariable=BasicSalary )
txtBasicSalary.grid(row=1,column=1)

lblOverTime= Label(LeftInsideLFLF ,font=('arial',12,'bold'),text="Over Time" ,fg='Steel Blue',bd=10, anchor='w')
lblOverTime.grid(row=2,column=0)
txtOverTime= Entry(LeftInsideLFLF ,font=('arial',12,'bold'),bd=10,width=18, bg='Powder Blue', justify='left',textvariable=OverTime )
txtOverTime.grid(row=2,column=1)

lblGrossPay= Label(LeftInsideLFLF ,font=('arial',12,'bold'),text="Gross Pay" ,fg='Steel Blue',bd=10, anchor='w')
lblGrossPay.grid(row=3,column=0)
txtGrossPay= Entry(LeftInsideLFLF ,font=('arial',12,'bold'),bd=10,width=18, bg='Powder Blue', justify='left',textvariable=GrossPay )
txtGrossPay.grid(row=3,column=1)

lblNetPay= Label(LeftInsideLFLF ,font=('arial',12,'bold'),text="Net Pay" ,fg='Steel Blue',bd=10, anchor='w')
lblNetPay.grid(row=4,column=0)
txtNetPay= Entry(LeftInsideLFLF ,font=('arial',12,'bold'),bd=10,width=18, bg='Powder Blue', justify='left',textvariable=NetPay )
txtNetPay.grid(row=4,column=1)
#========================INSIDE LFRF======================================================================================
lblTax= Label(LeftInsideRLLF ,font=('arial',12,'bold'),text="Tax" ,fg='Steel Blue',bd=10, anchor='w')
lblTax.grid(row=0,column=0)
txtTax= Entry(LeftInsideRLLF ,font=('arial',12,'bold'),bd=10,width=18, bg='Powder Blue', justify='left',textvariable=Tax )
txtTax.grid(row=0,column=1)

lblPension= Label(LeftInsideRLLF ,font=('arial',12,'bold'),text="Pension" ,fg='Steel Blue',bd=10, anchor='w')
lblPension.grid(row=1,column=0)
txtPension= Entry(LeftInsideRLLF ,font=('arial',12,'bold'),bd=10,width=18, bg='Powder Blue', justify='left',textvariable=Pension )
txtPension.grid(row=1,column=1)

lblStudentLoan= Label(LeftInsideRLLF ,font=('arial',12,'bold'),text="Student Loan" ,fg='Steel Blue',bd=10, anchor='w')
lblStudentLoan.grid(row=2,column=0)
txtStudentLoan= Entry(LeftInsideRLLF ,font=('arial',12,'bold'),bd=10,width=18, bg='Powder Blue', justify='left',textvariable=StudentLoan )
txtStudentLoan.grid(row=2,column=1)

lblNIPayment= Label(LeftInsideRLLF ,font=('arial',12,'bold'),text="NI Payment" ,fg='Steel Blue',bd=10, anchor='w')
lblNIPayment.grid(row=3,column=0)
txtNIPayment= Entry(LeftInsideRLLF ,font=('arial',12,'bold'),bd=10,width=18, bg='Powder Blue', justify='left',textvariable=NIPayment )
txtNIPayment.grid(row=3,column=1)

lblDeductions= Label(LeftInsideRLLF ,font=('arial',12,'bold'),text="Deductions" ,fg='Steel Blue',bd=10, anchor='w')
lblDeductions.grid(row=4,column=0)
txtDeductions= Entry(LeftInsideRLLF ,font=('arial',12,'bold'),bd=10,width=18, bg='Powder Blue', justify='left',textvariable=Deductions )
txtDeductions.grid(row=4,column=1)

#================================Right Side================================================================================
lblPostCode= Label(RightInsideLF ,font=('arial',12,'bold'),text="PostCode" ,fg='Steel Blue',bd=10, anchor='w')
lblPostCode.grid(row=0,column=0)
txtPostCode= Entry(RightInsideLF ,font=('arial',12,'bold'),bd=20,width=54,bg='Powder Blue', justify='left',textvariable=PostCode )
txtPostCode.grid(row=0,column=1)

lblGender= Label(RightInsideLF ,font=('arial',12,'bold'),text="Gender" ,fg='Steel Blue',bd=10, anchor='w')
lblGender.grid(row=1,column=0)
txtGender= Entry(RightInsideLF,font=('arial',12,'bold'),bd=20, width=54,bg='Powder Blue',justify='left',textvariable=Gender )
txtGender.grid(row=1,column=1)

#========================== Right inner Side=================================================================================

lblPaydate= Label(RightInsideLFLF ,font=('arial',12,'bold'),text="Pay Date" ,fg='Steel Blue',bd=10, anchor='w')
lblPaydate.grid(row=0,column=0)
txtPaydate= Entry(RightInsideLFLF,font=('arial',12,'bold'),bd=10, width=18,bg='Powder Blue',justify='left' ,textvariable=Paydate)
txtPaydate.grid(row=0,column=1)

lblTaxPeriod= Label(RightInsideLFLF ,font=('arial',12,'bold'),text="Tax Period" ,fg='Steel Blue',bd=10, anchor='w')
lblTaxPeriod.grid(row=1,column=0)
txtTaxPeriod= Entry(RightInsideLFLF,font=('arial',12,'bold'),bd=10, width=18,bg='Powder Blue',justify='left',textvariable=TaxPeriod )
txtTaxPeriod.grid(row=1,column=1)

lblNINumber= Label(RightInsideLFLF ,font=('arial',12,'bold'),text="NI Number" ,fg='Steel Blue',bd=10, anchor='w')
lblNINumber.grid(row=2,column=0)
txtNINumber= Entry(RightInsideLFLF,font=('arial',12,'bold'),bd=10, width=18,bg='Powder Blue',justify='left',textvariable=NINumber )
txtNINumber.grid(row=2,column=1)

lblNICode= Label(RightInsideLFLF ,font=('arial',12,'bold'),text="NICode" ,fg='Steel Blue',bd=10, anchor='w')
lblNICode.grid(row=3,column=0)
txtNICode= Entry(RightInsideLFLF,font=('arial',12,'bold'),bd=10, width=18,bg='Powder Blue',justify='left',textvariable=NICode )
txtNICode.grid(row=3,column=1)

lblTaxablePay= Label(RightInsideLFLF ,font=('arial',12,'bold'),text="Taxable Pay" ,fg='Steel Blue',bd=10, anchor='w')
lblTaxablePay.grid(row=4,column=0)
txtTaxablePay= Entry(RightInsideLFLF,font=('arial',12,'bold'),bd=10, width=18,bg='Powder Blue',justify='left',textvariable=TaxablePay )
txtTaxablePay.grid(row=4,column=1)

lblPensionablePay= Label(RightInsideLFLF ,font=('arial',12,'bold'),text="Pensionable Pay" ,fg='Steel Blue',bd=10, anchor='w')
lblPensionablePay.grid(row=5,column=0)
txtPensionablePay= Entry(RightInsideLFLF,font=('arial',12,'bold'),bd=10, width=18,bg='Powder Blue',justify='left',textvariable=PensionablePay )
txtPensionablePay.grid(row=5,column=1)

lblOtherPaymentsDue= Label(RightInsideLFLF ,font=('arial',12,'bold'),text="Other Payments Due" ,fg='Steel Blue',bd=10, anchor='w')
lblOtherPaymentsDue.grid(row=6,column=0)
txtOtherPaymentsDue= Entry(RightInsideLFLF,font=('arial',12,'bold'),bd=10, width=18,bg='Powder Blue',justify='left',textvariable=OtherPaymentsDue )
txtOtherPaymentsDue.grid(row=6,column=1)

btnWagePayment= Button (RightInsideRLLF ,padx=8 ,bd=8 ,fg="black",font=('arial',12,'bold') ,width=14, text= "Wage Payment",bg= 'sky blue', command=MonthlySalary).grid (row=0,column=0)

btnResetSystem= Button (RightInsideRLLF ,padx=8 ,bd=8 ,fg="black",font=('arial',12,'bold') ,width=14, text= "Reset System",bg= 'sky blue',command= Reset).grid (row=1,column=0)

btnPayReference= Button (RightInsideRLLF ,padx=8 ,bd=8 ,fg="black",font=('arial',12,'bold') ,width=14, text= "Pay Reference",bg= 'sky blue', command=PayRef).grid (row=2,column=0)

btnPayCode= Button (RightInsideRLLF ,padx=8 ,bd=8 ,fg="black",font=('arial',12,'bold') ,width=14, text= "Pay Code",bg= 'sky blue',command=PayPeriod).grid (row=3,column=0)
                
btnExit= Button (RightInsideRLLF ,padx=8 ,bd=8 ,fg="black",font=('arial',12,'bold') ,width=14, text= "Exit",bg= 'sky blue', command= Exit).grid (row=4,column=0)

payroll.mainloop()

