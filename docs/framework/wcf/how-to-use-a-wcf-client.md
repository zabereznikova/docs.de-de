---
title: 'Gewusst wie: Verwenden eines Windows Communication Foundation-Clients'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF clients [WCF], using
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0330c386730c6b0436196bb5b85162bc4621c214
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a>Gewusst wie: Verwenden eines Windows Communication Foundation-Clients
Dies ist die letzte von sechs Aufgaben, die zum Erstellen einer grundlegenden [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Anwendung erforderlich sind. Einen Überblick über alle sechs Aufgaben finden Sie unter der [Lernprogramm für erste Schritte](../../../docs/framework/wcf/getting-started-tutorial.md) Thema.  
  
 Nachdem der [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Proxy erstellt und konfiguriert wurde, kann eine Clientinstanz erstellt und die Clientanwendung kompiliert und für die Kommunikation mit einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst verwendet werden. In diesem Thema werden Verfahren zur Instanziierung und Verwendung eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clients beschrieben. Von dieser Prozedur werden drei Aktionen ausgeführt:  
  
1.  Instanziiert einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Client.  
  
2.  Die Dienstoperationen werden vom erstellten Proxy aufgerufen.  
  
3.  Nach Abschluss des Operationsaufrufs wird der Client beendet.  
  
### <a name="to-use-a-windows-communication-foundation-client"></a>So verwenden Sie einen Windows Communication Foundation-Client  
  
1.  Öffnen Sie im GettingStartedClient-Projekt die Datei "Program.cs" oder "Program.vb", und ersetzen Sie den vorhandenen Code durch den folgenden Code:  
  
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
  
     Beachten Sie die Using- oder Imports-Anweisung, mit der "GettingStartedClient.ServiceReference1" importiert wird. Dies importiert den Code, der durch "Dienstverweis hinzufügen" in Visual Studio generiert wird. Der Code instanziiert den WCF-Proxy und ruft dann die einzelnen Dienstvorgänge auf, die vom Rechnerdienst verfügbar gemacht werden, schließt den Proxy und beendet den Vorgang.  
  
 Sie haben nun das Lernprogramm abgeschlossen. Sie haben einen Dienstvertrag definiert, den Dienstvertrag implementiert, einen WCF-Proxy generiert, eine WCF-Clientanwendung konfiguriert und den Proxy zum Aufrufen von Dienstvorgängen verwendet. Um die Anwendung zu testen, führen Sie zuerst "GettingStartedHost" aus, um den Dienst zu starten, und dann "GettingStartedClient". Die Ausgabe von "GettingStartedHost" sollte wie folgt aussehen:  
  
```Output  
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714  
```  
  
 Die Ausgabe von "GettingStartedClient" sollte wie folgt aussehen:  
  
```Output  
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Clients](../../../docs/framework/wcf/building-clients.md)  
 [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Tutorial mit ersten Schritten](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Einfache WCF-Programmierung](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Vorgehensweise: Erstellen eines Duplexvertrags](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)
