---
title: Erwartete Ausnahmen
ms.date: 03/30/2017
ms.assetid: 299a6987-ae6b-43c6-987f-12b034b583ae
ms.openlocfilehash: 16b7a4029c9225984d71e5252605376d2d4b6d53
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832033"
---
# <a name="expected-exceptions"></a>Erwartete Ausnahmen
Dieses Beispiel zeigt, wie erwartete Ausnahmen beim Verwenden eines typisierten Clients abgefangen werden. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , das einen rechnerdienst implementiert. In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel zeigt das Abfangen und Behandeln von erwarteten Ausnahmen beider Typen, die korrekte Programme verarbeiten müssen: `TimeoutException` und `CommunicationException`.  
  
 Ausnahmen, die aus Kommunikationsmethoden in einem Windows Communication Foundation (WCF)-Client ausgelöst werden, sind entweder erwartet oder unerwartet. Unerwartete Ausnahmen umfassen katastrophale Fehler (wie `OutOfMemoryException`) und Programmierfehler (wie `ArgumentNullException` oder `InvalidOperationException`). Es ist in der Regel keine praktische Möglichkeit, unerwartete Fehler zu behandeln, in der Regel Sie nicht diese abfangen sollte beim Aufrufen einer WCF-Client-Kommunikation-Methode.  
  
 Erwartete Ausnahmen aus Kommunikationsmethoden in einem WCF-Client enthalten `TimeoutException`, `CommunicationException`, und eine abgeleitete Klasse von `CommunicationException`. Diese weisen ein Problem während der Kommunikation, die sicher behandelt werden kann, von der WCF-Client abgebrochen und ein Kommunikationsfehler gemeldet. Da diese Fehler durch externe Faktoren in jeder Anwendung verursacht werden können, müssen ordnungsgemäße Anwendungen diese Ausnahmen abfangen und wiederherstellen, wenn sie auftreten.  
  
 Es gibt verschiedene von `CommunicationException` abgeleitete Klassen, die ein Client auslösen kann. In manchen Fällen fangen Anwendungen auch einige von ihnen ab, um eine bestimmte Verarbeitung auszuführen, während sie andere Ausnahmen als `CommunicationException` behandeln lassen. Dies kann durchgeführt werden, indem zuerst Ausnahmen bestimmter Typen und dann `CommunicationException` in einer späteren Abfangklausel abgefangen werden.  
  
 Code, der eine Clientkommunikationsmethode aufruft, muss `TimeoutException` und `CommunicationException` abfangen. Eine Möglichkeit zum Umgang mit solchen Fehlern wäre, den Client abzubrechen und den Kommunikationsfehler zu melden.  
  
```csharp   
try  
{  
    ...  
    double result = client.Add(value1, value2);  
    ...  
    client.Close();  
}  
catch (TimeoutException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
catch (CommunicationException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
```  
  
 Wenn eine erwartete Ausnahme auftritt, kann der Client anschließend noch verwendbar oder nicht mehr verwendbar sein. Um zu bestimmen, ob der Client immer noch verwendbar ist, überprüfen Sie, dass die `State`-Eigenschaft `CommunicationState`.Opened ist. Wenn der Client immer noch geöffnet ist, dann ist er auch noch verwendbar. Andernfalls sollten Sie den Client abbrechen und alle Verweise auf ihn freigeben.  
  
> [!CAUTION]
>  Manchmal lässt sich beobachten, dass Clients mit einer Sitzung nach einer Ausnahme nicht mehr verwendbar sind, während Clients ohne eine Sitzung auch nach Auftreten einer Ausnahme oftmals noch verwendet werden können. Da es jedoch für keinen der beiden Fälle eine Garantie gibt, sollte die Anwendung &amp;#150; falls der Client nach einer Ausnahme weiter verwendet werden soll &amp;#150; mithilfe der `State`-Eigenschaft überprüfen, ob der Client weiterhin geöffnet ist.  
  
 Wenn Sie das Beispiel ausführen, werden die Antworten und Ausnahmen für den Vorgang im Konsolenfenster des Clients angezeigt.  
  
 Der Clientprozess führt zwei Szenarios aus, die beide versuchen, `Add` und anschließend `Divide` aufzurufen. Das erste Szenario simuliert ein Netzwerkproblem, indem der Client vor dem Aufruf von `Divide` abgebrochen wird. Das zweite Szenario verursacht einen Timeout-Zustand, indem ein so kurzes Timeout festgelegt wird, dass die Methode nicht abgeschlossen werden kann. Die erwartete Ausgabe vom Clientprozess lautet wie folgt:  
  
```  
Add(100,15.99) = 115.99  
Simulated network problem occurs...  
Got System.ServiceModel.CommunicationObjectAbortedException  
Add(100,15.99) = 115.99  
Set timeout too short for method to complete...  
Got System.TimeoutException  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ExpectedExceptions`  
  
