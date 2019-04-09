---
title: 'Tutorial: Verwenden Sie einen Windows Communication Foundation-client'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: fa9aa3612a8dc72623fc4ea4b1ea337ac773fa26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169968"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a><span data-ttu-id="50406-102">Tutorial: Verwenden Sie einen Windows Communication Foundation-client</span><span class="sxs-lookup"><span data-stu-id="50406-102">Tutorial: Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="50406-103">In diesem Tutorial wird beschrieben, die letzte von fünf Aufgaben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="50406-103">This tutorial describes the last of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="50406-104">Eine Übersicht über die Lernprogramme, finden Sie unter [Lernprogramm: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="50406-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="50406-105">Nachdem Sie erstellt und einen Windows Communication Foundation (WCF)-Proxy konfiguriert haben, erstellen Sie eine Clientinstanz, und Sie kompilieren Sie die Clientanwendung.</span><span class="sxs-lookup"><span data-stu-id="50406-105">After you've created and configured a Windows Communication Foundation (WCF) proxy, you create a client instance and compile the client application.</span></span> <span data-ttu-id="50406-106">Damit können Sie dann mit dem WCF-Dienst kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="50406-106">You then use it to communicate with the WCF service.</span></span> 

<span data-ttu-id="50406-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="50406-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="50406-108">Fügen Sie Code, um den WCF-Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="50406-108">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="50406-109">Testen Sie den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="50406-109">Test the WCF client.</span></span>

## <a name="add-code-to-use-the-wcf-client"></a><span data-ttu-id="50406-110">Hinzufügen von Code zum Verwenden des WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="50406-110">Add code to use the WCF client</span></span>

<span data-ttu-id="50406-111">Der Clientcode führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="50406-111">The client code does the following steps:</span></span>
- <span data-ttu-id="50406-112">Instanziiert den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="50406-112">Instantiates the WCF client.</span></span>
- <span data-ttu-id="50406-113">Die Dienstoperationen werden vom erstellten Proxy aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="50406-113">Calls the service operations from the generated proxy.</span></span>
- <span data-ttu-id="50406-114">Der Client wird geschlossen, nachdem der Vorgangsaufruf abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="50406-114">Closes the client after the operation call is completed.</span></span>

<span data-ttu-id="50406-115">Öffnen der **"Program.cs"** oder **"Module1.vb"** -Datei aus dem **"gettingstartedclient"** Projekts, und Ersetzen Sie den Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="50406-115">Open the **Program.cs** or **Module1.vb** file from the **GettingStartedClient** project and replace its code with the following code:</span></span>

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
Imports System
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

<span data-ttu-id="50406-116">Beachten Sie, dass die `using` (für Visual C#) oder `Imports` (für Visual Basic)-Anweisung, die importiert `GettingStartedClient.ServiceReference1`.</span><span class="sxs-lookup"><span data-stu-id="50406-116">Notice the `using` (for Visual C#) or `Imports` (for Visual Basic) statement that imports `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="50406-117">Diese Anweisung importiert den Code, der mit Visual Studio generiert die **Hinzufügen eines Dienstverweises** Funktion.</span><span class="sxs-lookup"><span data-stu-id="50406-117">This statement imports the code that Visual Studio generated with the **Add Service Reference** function.</span></span> <span data-ttu-id="50406-118">Der Code instanziiert den WCF-Proxy und ruft alle Dienstvorgänge, die vom rechnerdienst verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="50406-118">The code instantiates the WCF proxy and calls each of the service operations that the calculator service exposes.</span></span> <span data-ttu-id="50406-119">Klicken Sie dann den Proxy schließt, und das Programm beendet wird.</span><span class="sxs-lookup"><span data-stu-id="50406-119">It then closes the proxy and ends the program.</span></span>

## <a name="test-the-wcf-client"></a><span data-ttu-id="50406-120">Testen des WCF-Clients</span><span class="sxs-lookup"><span data-stu-id="50406-120">Test the WCF client</span></span>

### <a name="test-the-application-from-visual-studio"></a><span data-ttu-id="50406-121">Testen Sie die Anwendung aus Visual Studio</span><span class="sxs-lookup"><span data-stu-id="50406-121">Test the application from Visual Studio</span></span>

1. <span data-ttu-id="50406-122">Speichern Sie und erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="50406-122">Save and build the solution.</span></span>

2. <span data-ttu-id="50406-123">Wählen Sie die **GettingStartedLib** Ordner, und wählen Sie dann **als Startprojekt festlegen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="50406-123">Select the **GettingStartedLib** folder, and then select **Set as Startup Project** from the shortcut menu.</span></span>

3. <span data-ttu-id="50406-124">Von **Startprojekte**Option **GettingStartedLib** aus der Dropdown-Liste, und wählen Sie dann **ausführen** , oder drücken Sie **F5**.</span><span class="sxs-lookup"><span data-stu-id="50406-124">From **Startup Projects**, select **GettingStartedLib** from the drop-down list, then select **Run** or press **F5**.</span></span>

### <a name="test-the-application-from-a-command-prompt"></a><span data-ttu-id="50406-125">Testen Sie die Anwendung über eine Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="50406-125">Test the application from a command prompt</span></span>

1. <span data-ttu-id="50406-126">Öffnen Sie eine Eingabeaufforderung als Administrator, und navigieren Sie zu Ihrem Verzeichnis der Visual Studio-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="50406-126">Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.</span></span> 

2. <span data-ttu-id="50406-127">Zum Starten des Diensts: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span><span class="sxs-lookup"><span data-stu-id="50406-127">To start the service: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span></span>

3. <span data-ttu-id="50406-128">Um den Client zu starten: Öffnen Sie eine andere Eingabeaufforderung, navigieren Sie zu Ihrem Verzeichnis der Visual Studio-Projektmappe, und geben Sie *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span><span class="sxs-lookup"><span data-stu-id="50406-128">To start the client: Open another command prompt, navigate to your Visual Studio solution directory, then enter *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span></span>

   <span data-ttu-id="50406-129">*GettingStartedHost.exe* erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="50406-129">*GettingStartedHost.exe* produces the following output:</span></span>

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

   <span data-ttu-id="50406-130">*GettingStartedClient.exe* erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="50406-130">*GettingStartedClient.exe* produces the following output:</span></span>

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a><span data-ttu-id="50406-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="50406-131">Next steps</span></span>

<span data-ttu-id="50406-132">Sie haben jetzt alle Aufgaben in der WCF-erste-Schritte-Lernprogramm abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="50406-132">You've now completed all the tasks in the WCF get started tutorial.</span></span> <span data-ttu-id="50406-133">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="50406-133">In this tutorial, you learned how to:</span></span>

<span data-ttu-id="50406-134">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="50406-134">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="50406-135">Fügen Sie Code, um den WCF-Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="50406-135">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="50406-136">Testen Sie den WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="50406-136">Test the WCF client.</span></span>

<span data-ttu-id="50406-137">Wenn Sie Probleme oder Fehler in einem beliebigen Schritt verfügen, führen Sie die Schritte in den Artikel zur Problembehandlung, um sie zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="50406-137">If you have problems or errors in any of the steps, follow the steps in the troubleshooting article to fix them.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="50406-138">Problembehandlung bei den Get Schritte mit WCF-Lernprogramme</span><span class="sxs-lookup"><span data-stu-id="50406-138">Troubleshoot the Get started with WCF tutorials</span></span>](troubleshooting-the-getting-started-tutorial.md)
