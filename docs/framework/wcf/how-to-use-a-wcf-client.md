---
title: 'Gewusst wie: Verwenden eines Windows Communication Foundation-Clients'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF clients [WCF], using
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
caps.latest.revision: "38"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c4b0612cc18129f9f35ed3f475bca8941a20d3ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="48042-102">Gewusst wie: Verwenden eines Windows Communication Foundation-Clients</span><span class="sxs-lookup"><span data-stu-id="48042-102">How to: Use a Windows Communication Foundation Client</span></span>
<span data-ttu-id="48042-103">Dies ist die letzte von sechs Aufgaben, die zum Erstellen einer grundlegenden [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="48042-103">This is the last of six tasks required to create a basic [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="48042-104">Einen Überblick über alle sechs Aufgaben finden Sie unter der [Lernprogramm für erste Schritte](../../../docs/framework/wcf/getting-started-tutorial.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="48042-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="48042-105">Nachdem der [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Proxy erstellt und konfiguriert wurde, kann eine Clientinstanz erstellt und die Clientanwendung kompiliert und für die Kommunikation mit einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48042-105">Once a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] proxy has been created and configured, a client instance can be created and the client application can be compiled and used to communicate with the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="48042-106">In diesem Thema werden Verfahren zur Instanziierung und Verwendung eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clients beschrieben.</span><span class="sxs-lookup"><span data-stu-id="48042-106">This topic describes procedures for instantiating and using a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client.</span></span> <span data-ttu-id="48042-107">Von dieser Prozedur werden drei Aktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="48042-107">This procedure does three things:</span></span>  
  
1.  <span data-ttu-id="48042-108">Instanziiert einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Client.</span><span class="sxs-lookup"><span data-stu-id="48042-108">Instantiates a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client.</span></span>  
  
2.  <span data-ttu-id="48042-109">Die Dienstoperationen werden vom erstellten Proxy aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="48042-109">Calls the service operations from the generated proxy.</span></span>  
  
3.  <span data-ttu-id="48042-110">Nach Abschluss des Operationsaufrufs wird der Client beendet.</span><span class="sxs-lookup"><span data-stu-id="48042-110">Closes the client once the operation call is completed.</span></span>  
  
### <a name="to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="48042-111">So verwenden Sie einen Windows Communication Foundation-Client</span><span class="sxs-lookup"><span data-stu-id="48042-111">To use a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="48042-112">Öffnen Sie im GettingStartedClient-Projekt die Datei "Program.cs" oder "Program.vb", und ersetzen Sie den vorhandenen Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="48042-112">Open the Program.cs or Program.vb file from the GettingStartedClient project and replace the existing code with the following code:</span></span>  
  
    ```  
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
  
    ```  
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
  
     <span data-ttu-id="48042-113">Beachten Sie die Using- oder Imports-Anweisung, mit der "GettingStartedClient.ServiceReference1" importiert wird.</span><span class="sxs-lookup"><span data-stu-id="48042-113">Notice the using or imports statement that imports the GettingStartedClient.ServiceReference1.</span></span> <span data-ttu-id="48042-114">Dies importiert den Code, der durch "Dienstverweis hinzufügen" in Visual Studio generiert wird.</span><span class="sxs-lookup"><span data-stu-id="48042-114">This imports the code generated by Add Service Reference in Visual Studio.</span></span> <span data-ttu-id="48042-115">Der Code instanziiert den WCF-Proxy und ruft dann die einzelnen Dienstvorgänge auf, die vom Rechnerdienst verfügbar gemacht werden, schließt den Proxy und beendet den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="48042-115">The code instantiates the WCF proxy and then calls each of the service operations exposed by the calculator service, closes the proxy and terminates.</span></span>  
  
 <span data-ttu-id="48042-116">Sie haben nun das Lernprogramm abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="48042-116">You have now completed the tutorial.</span></span> <span data-ttu-id="48042-117">Sie haben einen Dienstvertrag definiert, den Dienstvertrag implementiert, einen WCF-Proxy generiert, eine WCF-Clientanwendung konfiguriert und den Proxy zum Aufrufen von Dienstvorgängen verwendet.</span><span class="sxs-lookup"><span data-stu-id="48042-117">You defined a service contract, implemented the service contract, generated a WCF proxy, configured a WCF client application, and then used the proxy to call service operations.</span></span> <span data-ttu-id="48042-118">Um die Anwendung zu testen, führen Sie zuerst "GettingStartedHost" aus, um den Dienst zu starten, und dann "GettingStartedClient".</span><span class="sxs-lookup"><span data-stu-id="48042-118">To test out the application first run GettingStartedHost to start the service and then run GettingStartedClient.</span></span> <span data-ttu-id="48042-119">Die Ausgabe von "GettingStartedHost" sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="48042-119">The output from GettingStartedHost should look like this:</span></span>  
  
```Output  
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714  
```  
  
 <span data-ttu-id="48042-120">Die Ausgabe von "GettingStartedClient" sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="48042-120">The output from GettingStartedClient should look like this:</span></span>  
  
```Output  
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.  
```  
  
## <a name="see-also"></a><span data-ttu-id="48042-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48042-121">See Also</span></span>  
 [<span data-ttu-id="48042-122">Erstellen von Clients</span><span class="sxs-lookup"><span data-stu-id="48042-122">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
 [<span data-ttu-id="48042-123">Vorgehensweise: Erstellen eines Clients</span><span class="sxs-lookup"><span data-stu-id="48042-123">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="48042-124">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="48042-124">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="48042-125">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="48042-125">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="48042-126">Vorgehensweise: Erstellen eines Duplexvertrags</span><span class="sxs-lookup"><span data-stu-id="48042-126">How to: Create a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="48042-127">Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag</span><span class="sxs-lookup"><span data-stu-id="48042-127">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [<span data-ttu-id="48042-128">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="48042-128">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="48042-129">Selbsthosting</span><span class="sxs-lookup"><span data-stu-id="48042-129">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
