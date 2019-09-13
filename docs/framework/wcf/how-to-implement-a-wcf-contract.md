---
title: 'Tutorial: Implementieren eines Windows Communication Foundation Service-Vertrags'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: 05923dc0a2223da5e5fcda483abc1ee1dd2d643f
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928708"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="3341c-102">Tutorial: Implementieren eines Windows Communication Foundation Service-Vertrags</span><span class="sxs-lookup"><span data-stu-id="3341c-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="3341c-103">In diesem Tutorial wird die zweite von fünf Aufgaben beschrieben, die zum Erstellen einer Basic Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3341c-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="3341c-104">Eine Übersicht über die Tutorials finden [Sie unter Tutorial: Beginnen Sie mit Windows Communication Foundation Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="3341c-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="3341c-105">Der nächste Schritt zum Erstellen einer WCF-Anwendung besteht darin, Code zum Implementieren der WCF-Dienst Schnittstelle hinzuzufügen, die Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3341c-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="3341c-106">In diesem Schritt erstellen Sie eine Klasse mit dem `CalculatorService` Namen, die die benutzerdefinierte `ICalculator` Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="3341c-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="3341c-107">Jede Methode im folgenden Code Ruft einen Rechner Vorgang auf und schreibt Text in die Konsole, um Sie zu testen.</span><span class="sxs-lookup"><span data-stu-id="3341c-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span> 

<span data-ttu-id="3341c-108">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="3341c-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="3341c-109">Fügen Sie Code hinzu, um den WCF-Dienstvertrag zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="3341c-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="3341c-110">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="3341c-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="3341c-111">Hinzufügen von Code zum Implementieren des WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="3341c-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="3341c-112">Öffnen Sie in **gettingstartedlib**die Datei **Service1.cs** oder **Service1. vb** , und ersetzen Sie den Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="3341c-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

## <a name="edit-appconfig"></a><span data-ttu-id="3341c-113">Bearbeiten von "App. config"</span><span class="sxs-lookup"><span data-stu-id="3341c-113">Edit App.config</span></span>

<span data-ttu-id="3341c-114">Bearbeiten Sie die Datei **app. config** in **gettingstartedlib** , um die Änderungen widerzuspiegeln, die Sie am Code vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="3341c-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>

- <span data-ttu-id="3341c-115">Für visuelle C# Projekte:</span><span class="sxs-lookup"><span data-stu-id="3341c-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="3341c-116">Ändern Sie Zeile 14 in`<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="3341c-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="3341c-117">Ändern Sie Zeile 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="3341c-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="3341c-118">Ändern Sie Zeile 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="3341c-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="3341c-119">Für Visual Basic-Projekte:</span><span class="sxs-lookup"><span data-stu-id="3341c-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="3341c-120">Ändern Sie Zeile 14 in`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="3341c-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="3341c-121">Ändern Sie Zeile 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="3341c-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="3341c-122">Ändern Sie Zeile 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="3341c-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="3341c-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3341c-123">Compile the code</span></span>

<span data-ttu-id="3341c-124">Erstellen Sie die Lösung, um sicherzustellen, dass keine Kompilierungsfehler vorliegen.</span><span class="sxs-lookup"><span data-stu-id="3341c-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="3341c-125">Wenn Sie Visual Studio verwenden, wählen Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen** (oder drücken Sie **STRG**+**UMSCHALT**+**B**).</span><span class="sxs-lookup"><span data-stu-id="3341c-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3341c-126">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3341c-126">Next steps</span></span>

<span data-ttu-id="3341c-127">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="3341c-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="3341c-128">Fügen Sie Code hinzu, um den WCF-Dienstvertrag zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="3341c-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="3341c-129">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="3341c-129">Build the solution.</span></span>

<span data-ttu-id="3341c-130">Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie den WCF-Dienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="3341c-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3341c-131">Tutorial: Hosten und Ausführen eines einfachen WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="3341c-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
