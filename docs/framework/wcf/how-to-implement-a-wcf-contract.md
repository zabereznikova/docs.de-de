---
title: 'Tutorial: Implementieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: debdeeac7064f5bae21622b2d9de84a4d8a0e66f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184070"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="c9580-102">Tutorial: Implementieren eines Windows Communication Foundation-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="c9580-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="c9580-103">In diesem Tutorial wird die zweite von fünf Aufgaben beschrieben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c9580-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="c9580-104">Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="c9580-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="c9580-105">Der nächste Schritt zum Erstellen einer WCF-Anwendung besteht darin, Code hinzuzufügen, um die WCF-Dienstschnittstelle zu implementieren, die Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="c9580-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="c9580-106">In diesem Schritt erstellen Sie `CalculatorService` eine Klasse mit `ICalculator` dem Namen, die die benutzerdefinierte Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="c9580-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="c9580-107">Jede Methode im folgenden Code ruft einen Rechnervorgang auf und schreibt Text in die Konsole, um ihn zu testen.</span><span class="sxs-lookup"><span data-stu-id="c9580-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span>

<span data-ttu-id="c9580-108">In diesem Tutorial lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c9580-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="c9580-109">Fügen Sie Code hinzu, um den WCF-Servicevertrag zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="c9580-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="c9580-110">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="c9580-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="c9580-111">Hinzufügen von Code zum Implementieren des WCF-Servicevertrags</span><span class="sxs-lookup"><span data-stu-id="c9580-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="c9580-112">Öffnen Sie unter **GettingStartedLib**die **Datei Service1.cs** oder **Service1.vb,** und ersetzen Sie ihren Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="c9580-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="c9580-113">App.config bearbeiten</span><span class="sxs-lookup"><span data-stu-id="c9580-113">Edit App.config</span></span>

<span data-ttu-id="c9580-114">Bearbeiten Sie **App.config** in **GettingStartedLib,** um die Änderungen widerzuspiegeln, die Sie am Code vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="c9580-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>

- <span data-ttu-id="c9580-115">Für Visual C-Projekte:</span><span class="sxs-lookup"><span data-stu-id="c9580-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="c9580-116">Änderung der Zeile 14 in`<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="c9580-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="c9580-117">Änderung der Zeile 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="c9580-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="c9580-118">Änderung der Zeile 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="c9580-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="c9580-119">Für Visual Basic-Projekte:</span><span class="sxs-lookup"><span data-stu-id="c9580-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="c9580-120">Änderung der Zeile 14 in`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="c9580-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="c9580-121">Änderung der Zeile 17 in`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="c9580-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="c9580-122">Änderung der Zeile 22 in`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="c9580-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="c9580-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c9580-123">Compile the code</span></span>

<span data-ttu-id="c9580-124">Erstellen Sie die Lösung, um sicherzustellen, dass keine Kompilierungsfehler vorliegen.</span><span class="sxs-lookup"><span data-stu-id="c9580-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="c9580-125">Wenn Sie Visual Studio verwenden, wählen Sie im Menü **Erstellen** **die Option Lösung erstellen** aus (oder drücken Sie **Strg**+**um Schicht**+**B**).</span><span class="sxs-lookup"><span data-stu-id="c9580-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c9580-126">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c9580-126">Next steps</span></span>

<span data-ttu-id="c9580-127">In diesem Tutorial haben Sie Folgendes gelernt:</span><span class="sxs-lookup"><span data-stu-id="c9580-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="c9580-128">Fügen Sie Code hinzu, um den WCF-Servicevertrag zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="c9580-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="c9580-129">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="c9580-129">Build the solution.</span></span>

<span data-ttu-id="c9580-130">Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie den WCF-Dienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9580-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c9580-131">Tutorial: Hosten und Ausführen eines grundlegenden WCF-Dienstes</span><span class="sxs-lookup"><span data-stu-id="c9580-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
