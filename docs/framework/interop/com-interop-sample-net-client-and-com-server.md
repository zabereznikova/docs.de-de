---
title: 'COM-Interop-Beispiel: .NET-Client und COM-Server'
description: Lesen Sie ein Codebeispiel, das zeigt, wie ein .NET-Client auf einen COM-Server zugreift, um eine Instanz einer COM-Co-Klasse zu erstellen und Klassenmitglieder aufzurufen, um Hypotheken zu berechnen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- interoperation with unmanaged code, samples
- COM interop, samples
ms.assetid: a3f752bb-8945-4e1b-8163-71def6e9f137
ms.openlocfilehash: ed8568116d189573a1903678726cb348fa062376
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282885"
---
# <a name="com-interop-sample-net-client-and-com-server"></a>COM-Interop-Beispiel: .NET-Client und COM-Server

In diesem Beispiel wird veranschaulicht, wie ein [.NET Client](#cpconcominteropsamplenetclientcomserveranchor1), der für den Zugriff auf einen [COM-Server](#cpconcominteropsamplenetclientcomserveranchor2) erstellt wurde, eine Instanz einer COM-Co-Klasse erstellt und Klassenmember aufruft, um Hypothekenberechnungen durchzuführen.  
  
 In diesem Beispiel erstellt der Client eine Instanz der **Loan**-Co-Klasse und ruft sie auf. Er übergibt vier Argumente (eine dieser vier ist gleich 0 (null)) an die Instanz und zeigt die Berechnungen. In diesem Abschnitt werden Codefragmente aus diesem Beispiel angezeigt.  
  
<a name="cpconcominteropsamplenetclientcomserveranchor1"></a>

## <a name="net-client"></a>.NET-Client  
  
```vb  
Imports System  
Imports Microsoft.VisualBasic  
Imports LoanLib  
  
Public Class LoanApp  
  
    Public Shared Sub Main()  
        Dim Args As String()  
        Args = System.Environment.GetCommandLineArgs()  
  
        Dim ln As New Loan()  
  
        If Args.Length < 5 Then  
            Console.WriteLine("Usage: ConLoan Balance Rate Term Payment")  
            Console.WriteLine(" Either Balance, Rate, Term, or Payment " _  
                                & "must be 0")  
            Exit Sub  
        End If  
  
        ln.OpeningBalance = Convert.ToDouble(Args(1))  
        ln.Rate = Convert.ToDouble(Args(2)) / 100.0  
        ln.Term = Convert.ToInt16(Args(3))  
        ln.Payment = Convert.ToDouble(Args(4))  
  
        If ln.OpeningBalance = 0.0 Then  
            ln.ComputeOpeningBalance()  
        End If  
        If ln.Rate = 0.0 Then  
            ln.ComputeRate()  
        End If  
        If ln.Term = 0 Then  
            ln.ComputeTerm()  
        End If  
        If ln.Payment = 0.0 Then  
            ln.ComputePayment()  
        End If
        Console.WriteLine("Balance = {0,10:0.00}", ln.OpeningBalance)  
        Console.WriteLine("Rate    = {0,10:0.0%}", ln.Rate)  
        Console.WriteLine("Term    = {0,10:0.00}", ln.Term)  
        Console.WriteLine("Payment = {0,10:0.00}" & ControlChars.Cr, _  
                          ln.Payment)  
  
        Dim MorePmts As Boolean  
        Dim Balance As Double = 0.0  
        Dim Principal As Double = 0.0  
        Dim Interest As Double = 0.0  
  
        Console.WriteLine("{0,4}{1,10}{2,12}{3,10}{4,12}", _  
           "Nbr", "Payment", "Principal", "Interest", "Balance")  
        Console.WriteLine("{0,4}{1,10}{2,12}{3,10}{4,12}", _  
           "---", "-------", "---------", "--------", "-------")  
  
        MorePmts = ln.GetFirstPmtDistribution(ln.Payment, Balance, _  
           Principal, Interest)  
  
        Dim PmtNbr As Short  
  
        While MorePmts  
  
            Console.WriteLine("{0,4}{1,10:0.00}{2,12:0.00}{3,10:0.00}" _  
              & "{4,12:0.00}", PmtNbr, ln.Payment, Principal, Interest,  
              Balance)  
            MorePmts = ln.GetNextPmtDistribution(ln.Payment, Balance, _  
              Principal, Interest)  
            PmtNbr += CShort(1)  
        End While  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using LoanLib;  
  
public class LoanApp {  
   public static void Main(String[] Args) {  
  
      Loan ln = new Loan();  
  
      if (Args.Length < 4)
      {  
         Console.WriteLine("Usage: ConLoan Balance Rate Term Payment");  
         Console.WriteLine("    Either Balance, Rate, Term, or Payment
            must be 0");  
         return;  
      }  
  
      ln.OpeningBalance = Convert.ToDouble(Args[0]);  
      ln.Rate = Convert.ToDouble(Args[1])/100.0;  
      ln.Term = Convert.ToInt16(Args[2]);  
      ln.Payment = Convert.ToDouble(Args[3]);  
  
      if (ln.OpeningBalance == 0.00) ln.ComputeOpeningBalance();  
      if (ln.Rate == 0.00) ln.ComputeRate();  
      if (ln.Term == 0) ln.ComputeTerm();  
      if (ln.Payment == 0.00) ln.ComputePayment();  
  
      Console.WriteLine("Balance = {0,10:0.00}", ln.OpeningBalance);  
      Console.WriteLine("Rate    = {0,10:0.0%}", ln.Rate);  
      Console.WriteLine("Term    = {0,10:0.00}", ln.Term);  
      Console.WriteLine("Payment = {0,10:0.00}\n", ln.Payment);  
  
      bool MorePmts;  
      double Balance = 0.0;  
      double Principal = 0.0;  
      double Interest = 0.0;  
  
      Console.WriteLine("{0,4}{1,10}{2,12}{3,10}{4,12}", "Nbr", "Payment",  
        "Principal", "Interest", "Balance");  
      Console.WriteLine("{0,4}{1,10}{2,12}{3,10}{4,12}", "---", "-------",  
        "---------", "--------", "-------");  
  
      MorePmts = ln.GetFirstPmtDistribution(ln.Payment, out Balance,
        out Principal, out Interest);  
  
      for (short PmtNbr = 1; MorePmts; PmtNbr++) {  
         Console.WriteLine("{0,4}{1,10:0.00}{2,12:0.00}{3,10:0.00}  
           {4,12:0.00}", PmtNbr, ln.Payment, Principal, Interest,  
            Balance);  
         MorePmts = ln.GetNextPmtDistribution(ln.Payment, ref Balance,
           out Principal, out Interest);
      }  
    }  
}  
```  
  
<a name="cpconcominteropsamplenetclientcomserveranchor2"></a>

## <a name="com-server"></a>COM-Server  
  
```cpp  
// Loan.cpp : Implementation of CLoan  
#include "stdafx.h"  
#include "math.h"  
#include "LoanLib.h"  
#include "Loan.h"  
  
static double Round(double value, short digits);
  
STDMETHODIMP CLoan::get_OpeningBalance(double *pVal)  
{  
    *pVal = OpeningBalance;  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::put_OpeningBalance(double newVal)  
{  
    OpeningBalance = newVal;  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::get_Rate(double *pVal)  
{  
    *pVal = Rate;  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::put_Rate(double newVal)  
{  
    Rate = newVal;  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::get_Payment(double *pVal)  
{  
    *pVal = Payment;  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::put_Payment(double newVal)  
{  
    Payment = newVal;  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::get_Term(short *pVal)  
{  
    *pVal = Term;  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::put_Term(short newVal)  
{  
    Term = newVal;  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::ComputePayment(double *pVal)  
{  
    Payment = Round(OpeningBalance * (Rate /
        (1 - pow((1 + Rate), -Term))),2);  
    *pVal = Payment;  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::ComputeOpeningBalance(double *pVal)  
{  
    OpeningBalance = Round(Payment / (Rate /
        (1 - pow((1 + Rate), -Term))),2);  
    *pVal = OpeningBalance ;  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::ComputeRate(double *pVal)  
{  
    double DesiredPayment = Payment;  
  
    for (Rate = 0.001; Rate < 28.0; Rate += 0.001)  
    {  
        Payment = Round(OpeningBalance * (Rate /
         (1 - pow((1 + Rate), -Term))),2);  
  
        if (Payment >= DesiredPayment)  
            break;  
    }  
  
    *pVal = Rate;
    return S_OK;  
}  
  
STDMETHODIMP CLoan::ComputeTerm(short *pVal)  
{  
    double DesiredPayment = Payment;  
    for (Term = 1; Term < 480 ; Term ++)  
    {  
        Payment = Round(OpeningBalance * (Rate /
         (1 - pow((1 + Rate), -Term))),2);  
        if (Payment <= DesiredPayment)  
            break;  
    }  
    *pVal = Term;
    return S_OK;  
}  
  
STDMETHODIMP CLoan::GetFirstPmtDistribution(double PmtAmt, double *Balance, double *PrinPortion, double *IntPortion, VARIANT_BOOL *pVal)  
{  
    *Balance = OpeningBalance;  
    GetNextPmtDistribution(PmtAmt, Balance, PrinPortion, IntPortion,
      pVal);  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::GetNextPmtDistribution(double PmtAmt, double *Balance, double *PrinPortion, double *IntPortion, VARIANT_BOOL *pVal)  
{  
    *IntPortion = Round(*Balance * Rate, 2);  
    *PrinPortion = Round(PmtAmt - *IntPortion, 2);  
    *Balance = Round(*Balance - *PrinPortion, 2);  
  
    if (*Balance <= 0.0)  
        *pVal = FALSE;  
    else  
        *pVal = TRUE;  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::get_RiskRating(BSTR *pVal)  
{  
    *pVal = (BSTR)RiskRating;  
    return S_OK;  
}  
  
STDMETHODIMP CLoan::put_RiskRating(BSTR newVal)  
{  
    RiskRating = newVal;  
    return S_OK;  
}  
static double Round(double value, short digits)
{  
    double factor = pow(10, digits);  
    return floor(value * factor + 0.5)/factor;  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- [Verfügbarmachen von COM-Komponenten für .NET Framework](exposing-com-components.md)
