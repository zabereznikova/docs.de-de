---
title: 'Tutorial: Implementieren eines Windows Communication Foundation-Dienstvertrags'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: fa8c5457c636d7f37215f0d4b4fdbb1c96c9481e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929052"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="c8fc6-102">Tutorial: Implementieren eines Windows Communication Foundation-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="c8fc6-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="c8fc6-103">In diesem Tutorial wird beschrieben, die zweite von fünf Schritte zur Erstellung einer grundlegenden Windows Communication Foundation (WCF)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c8fc6-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="c8fc6-104">Eine Übersicht über die Lernprogramme, finden Sie unter [Lernprogramm: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="c8fc6-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="c8fc6-105">Der nächste Schritt zum Erstellen einer WCF-Anwendung ist, Code hinzufügen, um die WCF-Dienstschnittstelle implementiert, die Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="c8fc6-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="c8fc6-106">In diesem Schritt erstellen Sie eine Klasse namens `CalculatorService` , implementiert der benutzerdefinierte `ICalculator` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c8fc6-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="c8fc6-107">Jede Methode in der folgende Code Ruft eine rechnervorgang und schreibt Text in der Konsole, um sie zu testen.</span><span class="sxs-lookup"><span data-stu-id="c8fc6-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span> 

<span data-ttu-id="c8fc6-108">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="c8fc6-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="c8fc6-109">Fügen Sie Code zum Implementieren des WCF-Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="c8fc6-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="c8fc6-110">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="c8fc6-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="c8fc6-111">Hinzufügen von Code zum Implementieren des WCF-Dienstvertrags</span><span class="sxs-lookup"><span data-stu-id="c8fc6-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="c8fc6-112">In **GettingStartedLib**öffnen die **Service1.cs** oder **Service1.vb** -Datei und Ersetzen Sie den Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="c8fc6-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="c8fc6-113">Bearbeiten Sie die Datei "App.config"</span><span class="sxs-lookup"><span data-stu-id="c8fc6-113">Edit App.config</span></span>

<span data-ttu-id="c8fc6-114">Bearbeiten Sie **"App.config"** in **GettingStartedLib** entsprechend die Änderungen, die Sie am Code vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="c8fc6-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>
- <span data-ttu-id="c8fc6-115">Für visuelle C# Projekte:</span><span class="sxs-lookup"><span data-stu-id="c8fc6-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="c8fc6-116">Ändern Sie Zeile 14 `<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="c8fc6-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="c8fc6-117">Ändern Sie Zeile 17 in `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="c8fc6-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="c8fc6-118">Ändern Sie Zeile 22 in `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="c8fc6-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="c8fc6-119">Für Visual Basic-Projekte:</span><span class="sxs-lookup"><span data-stu-id="c8fc6-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="c8fc6-120">Ändern Sie Zeile 14 `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="c8fc6-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="c8fc6-121">Ändern Sie Zeile 17 in `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="c8fc6-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="c8fc6-122">Ändern Sie Zeile 22 in `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="c8fc6-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="c8fc6-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c8fc6-123">Compile the code</span></span>

<span data-ttu-id="c8fc6-124">Erstellen Sie die Projektmappe aus, um sicherzustellen, dass Kompilierungsfehler vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c8fc6-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="c8fc6-125">Wenn Sie Visual Studio verwenden, sind die **erstellen** Menü die Option **Projektmappe** (oder drücken Sie **STRG**+**UMSCHALT** + **B**).</span><span class="sxs-lookup"><span data-stu-id="c8fc6-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c8fc6-126">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c8fc6-126">Next steps</span></span>

<span data-ttu-id="c8fc6-127">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="c8fc6-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="c8fc6-128">Fügen Sie Code zum Implementieren des WCF-Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="c8fc6-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="c8fc6-129">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="c8fc6-129">Build the solution.</span></span>

<span data-ttu-id="c8fc6-130">Fahren Sie fort mit dem nächsten Tutorial erfahren, wie den WCF-Dienst ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8fc6-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c8fc6-131">Tutorial: Hosten und Ausführen eines grundlegenden WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="c8fc6-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
