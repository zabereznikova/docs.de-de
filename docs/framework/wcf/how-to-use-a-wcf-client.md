---
title: 'Gewusst wie: Verwenden eines Windows Communication Foundation-Clients'
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 12e911fb899cb85121c129b762828cdda01e64f1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47112665"
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="7c4fc-102">Gewusst wie: Verwenden eines Windows Communication Foundation-Clients</span><span class="sxs-lookup"><span data-stu-id="7c4fc-102">How to: Use a Windows Communication Foundation Client</span></span>

<span data-ttu-id="7c4fc-103">Dies ist die letzte von sechs Aufgaben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-103">This is the last of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="7c4fc-104">Eine Übersicht über alle sechs Aufgaben finden Sie im Artikel [Getting Started Tutorial (Tutorial: Erste Schritte)](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="7c4fc-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="7c4fc-105">Nachdem Sie ein Windows Communication Foundation (WCF)-Proxy erstellt und konfiguriert wurde, kann eine Clientinstanz erstellt werden, und die Clientanwendung kompiliert und zur Kommunikation mit den WCF-Dienst verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-105">Once a Windows Communication Foundation (WCF) proxy has been created and configured, a client instance can be created and the client application can be compiled and used to communicate with the WCF service.</span></span> <span data-ttu-id="7c4fc-106">Dieses Thema beschreibt Verfahren zur Instanziierung und Verwendung eines WCF-Clients.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-106">This topic describes procedures for instantiating and using a WCF client.</span></span> <span data-ttu-id="7c4fc-107">Von dieser Prozedur werden drei Aktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="7c4fc-107">This procedure does three things:</span></span>

1.  <span data-ttu-id="7c4fc-108">Instanziiert einen WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-108">Instantiates a WCF client.</span></span>

2.  <span data-ttu-id="7c4fc-109">Die Dienstoperationen werden vom erstellten Proxy aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-109">Calls the service operations from the generated proxy.</span></span>

3.  <span data-ttu-id="7c4fc-110">Nach Abschluss des Operationsaufrufs wird der Client beendet.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-110">Closes the client once the operation call is completed.</span></span>

## <a name="use-a-windows-communication-foundation-client"></a><span data-ttu-id="7c4fc-111">Verwenden Sie einen Windows Communication Foundation-client</span><span class="sxs-lookup"><span data-stu-id="7c4fc-111">Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="7c4fc-112">Öffnen Sie im GettingStartedClient-Projekt die Datei "Program.cs" oder "Program.vb", und ersetzen Sie den vorhandenen Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="7c4fc-112">Open the Program.cs or Program.vb file from the GettingStartedClient project and replace the existing code with the following code:</span></span>

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

            //Step 3: Closing the client gracefully closes the connection and cleans up resources.
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
Imports GettingStartedClientVB2.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy
        Dim Client As New CalculatorClient()

        'Step 2: Call the service operations.
        'Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        'Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        'Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        'Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Closing the client gracefully closes the connection and cleans up resources.
        Client.Close()

        Console.WriteLine()
        Console.WriteLine("Press <ENTER> to terminate client.")
        Console.ReadLine()

    End Sub

End Module
```

<span data-ttu-id="7c4fc-113">Beachten Sie, dass die `using` oder `Imports` -Anweisung, die importiert die `GettingStartedClient.ServiceReference1`.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-113">Notice the `using` or `Imports` statement that imports the `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="7c4fc-114">Dadurch wird die vom generierten Code importiert **Hinzufügen eines Dienstverweises** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-114">This imports the code generated by **Add Service Reference** in Visual Studio.</span></span> <span data-ttu-id="7c4fc-115">Der Code instanziiert den WCF-Proxy und klicken Sie dann Ruft alle vom rechnerdienst verfügbar gemachten Dienstvorgänge schließt den Proxy und beendet wird.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-115">The code instantiates the WCF proxy and then calls each of the service operations exposed by the calculator service, closes the proxy, and terminates.</span></span>

<span data-ttu-id="7c4fc-116">Sie haben nun das Lernprogramm abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-116">You have now completed the tutorial.</span></span> <span data-ttu-id="7c4fc-117">Sie haben einen Dienstvertrag definiert, den Dienstvertrag implementiert, einen WCF-Proxy generiert, eine WCF-Clientanwendung konfiguriert und den Proxy zum Aufrufen von Dienstvorgängen verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c4fc-117">You defined a service contract, implemented the service contract, generated a WCF proxy, configured a WCF client application, and then used the proxy to call service operations.</span></span> <span data-ttu-id="7c4fc-118">Um die Anwendung zu testen, müssen Sie zuerst führen Sie die GettingStartedHost zum Starten des Diensts, und führen Sie dann "gettingstartedclient aus".</span><span class="sxs-lookup"><span data-stu-id="7c4fc-118">To test out the application, first run GettingStartedHost to start the service and then run GettingStartedClient.</span></span>

<span data-ttu-id="7c4fc-119">Die Ausgabe von "GettingStartedHost" sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="7c4fc-119">The output from GettingStartedHost should look like this:</span></span>

```text
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714
```

<span data-ttu-id="7c4fc-120">Die Ausgabe von "GettingStartedClient" sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="7c4fc-120">The output from GettingStartedClient should look like this:</span></span>

```text
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.
```

## <a name="see-also"></a><span data-ttu-id="7c4fc-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c4fc-121">See also</span></span>

- [<span data-ttu-id="7c4fc-122">Erstellen von Clients</span><span class="sxs-lookup"><span data-stu-id="7c4fc-122">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)
- [<span data-ttu-id="7c4fc-123">Vorgehensweise: Erstellen eines Clients</span><span class="sxs-lookup"><span data-stu-id="7c4fc-123">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="7c4fc-124">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="7c4fc-124">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)
- [<span data-ttu-id="7c4fc-125">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="7c4fc-125">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="7c4fc-126">Vorgehensweise: Erstellen eines Duplexvertrags</span><span class="sxs-lookup"><span data-stu-id="7c4fc-126">How to: Create a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="7c4fc-127">Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag</span><span class="sxs-lookup"><span data-stu-id="7c4fc-127">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="7c4fc-128">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="7c4fc-128">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="7c4fc-129">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="7c4fc-129">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)