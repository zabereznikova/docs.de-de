---
title: 'Tutorial: Verwenden eines Windows Communication Foundation Clients'
description: Erfahren Sie, wie Sie eine Client Instanz erstellen, die Anwendung kompilieren und mit einem Dienst im Rahmen einer Reihe von Artikeln über das Erstellen einer WCF-Anwendung kommunizieren.
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 5c94d5f8af679580c4194aaaadeda759098953d2
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244334"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a><span data-ttu-id="ff057-103">Tutorial: Verwenden eines Windows Communication Foundation Clients</span><span class="sxs-lookup"><span data-stu-id="ff057-103">Tutorial: Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="ff057-104">In diesem Tutorial werden die letzten fünf Aufgaben beschrieben, die zum Erstellen einer Basic Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ff057-104">This tutorial describes the last of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="ff057-105">Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Einstieg in Windows Communication Foundation Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ff057-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="ff057-106">Nachdem Sie einen Windows Communication Foundation (WCF)-Proxy erstellt und konfiguriert haben, erstellen Sie eine Client Instanz, und kompilieren Sie die Client Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ff057-106">After you've created and configured a Windows Communication Foundation (WCF) proxy, you create a client instance and compile the client application.</span></span> <span data-ttu-id="ff057-107">Anschließend verwenden Sie Sie, um mit dem WCF-Dienst zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="ff057-107">You then use it to communicate with the WCF service.</span></span>

<span data-ttu-id="ff057-108">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="ff057-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ff057-109">Fügen Sie Code zur Verwendung des WCF-Clients hinzu.</span><span class="sxs-lookup"><span data-stu-id="ff057-109">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="ff057-110">Testen Sie den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="ff057-110">Test the WCF client.</span></span>

## <a name="add-code-to-use-the-wcf-client"></a><span data-ttu-id="ff057-111">Hinzufügen von Code zur Verwendung des WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="ff057-111">Add code to use the WCF client</span></span>

<span data-ttu-id="ff057-112">Der Client Code führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ff057-112">The client code does the following steps:</span></span>

- <span data-ttu-id="ff057-113">Instanziiert den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="ff057-113">Instantiates the WCF client.</span></span>
- <span data-ttu-id="ff057-114">Die Dienstoperationen werden vom erstellten Proxy aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ff057-114">Calls the service operations from the generated proxy.</span></span>
- <span data-ttu-id="ff057-115">Schließt den Client, nachdem der Vorgang aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ff057-115">Closes the client after the operation call is completed.</span></span>

<span data-ttu-id="ff057-116">Öffnen Sie die Datei **Program.cs** oder **Module1. vb** aus dem **gettingstartedclient** -Projekt, und ersetzen Sie den Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="ff057-116">Open the **Program.cs** or **Module1.vb** file from the **GettingStartedClient** project and replace its code with the following code:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using GettingStartedClient.ServiceReference1;

namespace GettingStartedClient
{
    class Program
    {
        static void Main(string[] args)
        {
            //Step 1: Create an instance of the WCF proxy.
            CalculatorClient client = new CalculatorClient();

            // Step 2: Call the service operations.
            // Call the Add service operation.
            double value1 = 100.00D;
            double value2 = 15.99D;
            double result = client.Add(value1, value2);
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

            // Call the Subtract service operation.
            value1 = 145.00D;
            value2 = 76.54D;
            result = client.Subtract(value1, value2);
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

            // Call the Multiply service operation.
            value1 = 9.00D;
            value2 = 81.25D;
            result = client.Multiply(value1, value2);
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

            // Call the Divide service operation.
            value1 = 22.00D;
            value2 = 7.00D;
            result = client.Divide(value1, value2);
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

            // Step 3: Close the client to gracefully close the connection and clean up resources.
            Console.WriteLine("\nPress <Enter> to terminate the client.");
            Console.ReadLine();
            client.Close();
        }
    }
}
```

```vb
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClient.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy.
        Dim Client As New CalculatorClient()

        ' Step 2: Call the service operations.
        ' Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        ' Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        ' Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        ' Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Close the client to gracefully close the connection and clean up resources.
        Console.WriteLine()
        Console.WriteLine("Press <Enter> to terminate the client.")
        Console.ReadLine()
        Client.Close()

    End Sub

End Module
```

<span data-ttu-id="ff057-117">Beachten Sie die- `using` Anweisung (für Visual c#) oder die- `Imports` Anweisung (for Visual Basic), die importiert `GettingStartedClient.ServiceReference1` .</span><span class="sxs-lookup"><span data-stu-id="ff057-117">Notice the `using` (for Visual C#) or `Imports` (for Visual Basic) statement that imports `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="ff057-118">Diese Anweisung importiert den Code, der von Visual Studio mit der **Dienstverweis hinzufügen** -Funktion generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ff057-118">This statement imports the code that Visual Studio generated with the **Add Service Reference** function.</span></span> <span data-ttu-id="ff057-119">Der Code instanziiert den WCF-Proxy und ruft jeden der Dienst Vorgänge auf, die der Rechner Dienst verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="ff057-119">The code instantiates the WCF proxy and calls each of the service operations that the calculator service exposes.</span></span> <span data-ttu-id="ff057-120">Anschließend wird der Proxy geschlossen und das Programm beendet.</span><span class="sxs-lookup"><span data-stu-id="ff057-120">It then closes the proxy and ends the program.</span></span>

## <a name="test-the-wcf-client"></a><span data-ttu-id="ff057-121">Testen des WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="ff057-121">Test the WCF client</span></span>

### <a name="test-the-application-from-visual-studio"></a><span data-ttu-id="ff057-122">Testen der Anwendung in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ff057-122">Test the application from Visual Studio</span></span>

1. <span data-ttu-id="ff057-123">Speichern und erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="ff057-123">Save and build the solution.</span></span>

2. <span data-ttu-id="ff057-124">Wählen Sie den Ordner **gettingstartedlib** aus, und wählen Sie dann im Kontextmenü die Option **als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="ff057-124">Select the **GettingStartedLib** folder, and then select **Set as Startup Project** from the shortcut menu.</span></span>

3. <span data-ttu-id="ff057-125">Wählen Sie in **Start Projekten**in der Dropdown Liste **gettingstartedlib** aus, und wählen Sie dann **Ausführen** aus, oder drücken Sie **F5**.</span><span class="sxs-lookup"><span data-stu-id="ff057-125">From **Startup Projects**, select **GettingStartedLib** from the drop-down list, then select **Run** or press **F5**.</span></span>

### <a name="test-the-application-from-a-command-prompt"></a><span data-ttu-id="ff057-126">Testen der Anwendung über eine Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="ff057-126">Test the application from a command prompt</span></span>

1. <span data-ttu-id="ff057-127">Öffnen Sie eine Eingabeaufforderung als Administrator, und navigieren Sie dann zu Ihrem Visual Studio-Projektmappenverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ff057-127">Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.</span></span>

2. <span data-ttu-id="ff057-128">Geben Sie *GettingStartedHost\bin\Debug\GettingStartedHost.exe*ein, um den Dienst zu starten.</span><span class="sxs-lookup"><span data-stu-id="ff057-128">To start the service: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span></span>

3. <span data-ttu-id="ff057-129">So starten Sie den-Client: Öffnen Sie eine andere Eingabeaufforderung, navigieren Sie zu Ihrem Visual Studio-Projektmappenverzeichnis, und geben Sie *GettingStartedClient\bin\Debug\GettingStartedClient.exe*</span><span class="sxs-lookup"><span data-stu-id="ff057-129">To start the client: Open another command prompt, navigate to your Visual Studio solution directory, then enter *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span></span>

   <span data-ttu-id="ff057-130">*GettingStartedHost.exe* erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ff057-130">*GettingStartedHost.exe* produces the following output:</span></span>

   ```text
   The service is ready.
   Press <Enter> to terminate the service.

   Received Add(100,15.99)
   Return: 115.99
   Received Subtract(145,76.54)
   Return: 68.46
   Received Multiply(9,81.25)
   Return: 731.25
   Received Divide(22,7)
   Return: 3.14285714285714
   ```

   <span data-ttu-id="ff057-131">*GettingStartedClient.exe* erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ff057-131">*GettingStartedClient.exe* produces the following output:</span></span>

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a><span data-ttu-id="ff057-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ff057-132">Next steps</span></span>

<span data-ttu-id="ff057-133">Sie haben jetzt alle Aufgaben im WCF-Tutorial "Get Started" abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ff057-133">You've now completed all the tasks in the WCF get started tutorial.</span></span> <span data-ttu-id="ff057-134">In diesem Tutorial haben Sie Folgendes gelernt:</span><span class="sxs-lookup"><span data-stu-id="ff057-134">In this tutorial, you learned how to:</span></span>

<span data-ttu-id="ff057-135">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="ff057-135">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ff057-136">Fügen Sie Code zur Verwendung des WCF-Clients hinzu.</span><span class="sxs-lookup"><span data-stu-id="ff057-136">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="ff057-137">Testen Sie den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="ff057-137">Test the WCF client.</span></span>

<span data-ttu-id="ff057-138">Wenn in einem der Schritte Probleme oder Fehler auftreten, führen Sie die Schritte im Artikel zur Problembehandlung aus, um Sie zu beheben.</span><span class="sxs-lookup"><span data-stu-id="ff057-138">If you have problems or errors in any of the steps, follow the steps in the troubleshooting article to fix them.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ff057-139">Behandeln von Problemen mit den Tutorials für die ersten Schritte mit WCF</span><span class="sxs-lookup"><span data-stu-id="ff057-139">Troubleshoot the Get started with WCF tutorials</span></span>](troubleshooting-the-getting-started-tutorial.md)
