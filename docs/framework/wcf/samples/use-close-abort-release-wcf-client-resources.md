---
title: Verwenden Sie schließen "und" Abort um WCF-Client-Ressourcen freizugeben.
description: Dispose kann Fehler und Ausnahmen auslösen, wenn Netzwerkprobleme auftreten. Die kann unerwünschtes Verhalten führen. Stattdessen verwenden Sie, schließen, und abgebrochen Sie wird, um die Clientressourcen freigeben, wenn das Netzwerk ein Fehler aufgetreten ist.
ms.date: 11/12/2018
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
ms.openlocfilehash: 4996ccba955d7946bb76b8124b8b28d803b6f3e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736428"
---
# <a name="close-and-abort-release-resources-safely-when-network-connections-have-dropped"></a>Schließen und Abbruch Freigeben von Ressourcen sicher verwendet werden, wenn Netzwerkverbindungen gelöscht haben
Dieses Beispiel veranschaulicht die Verwendung der `Close` und `Abort` Methoden zum Bereinigen von Ressourcen für die Verwendung eines typisierten Clients. Die `using` Anweisung Ausnahmen verursacht, wenn die Netzwerkverbindung nicht robust ist. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , das einen rechnerdienst implementiert. In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel werden zwei häufige Probleme veranschaulicht, die beim Verwenden der C#-Anweisung "using" mit typisierten Clients auftreten. Außerdem wird Code bereitgestellt, mit dem die Bereinigung nach Ausnahmen korrekt ausgeführt werden kann.  
  
 Die C#-Anweisung "using" führt zu einem Aufruf von `Dispose`(). Dies ist das Gleiche wie `Close`(). Dies kann zu Ausnahmen führen, wenn ein Netzwerkfehler auftritt. Da der Aufruf von `Dispose`() implizit an der schließenden Klammer des "using"-Blocks erfolgt, wird diese Quelle für Ausnahmen beim Schreiben oder Lesen des Codes häufig nicht bemerkt. Dies stellt eine potenzielle Quelle für Anwendungsfehler dar.  
  
 Das erste Problem (in der `DemonstrateProblemUsingCanThrow`-Methode dargestellt) liegt darin, dass die schließende Klammer eine Ausnahme auslöst und der Code nach der schließenden Klammer nicht ausgeführt wird:  
  
```csharp   
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
} // <-- this line might throw  
Console.WriteLine("Hope this code wasn't important, because it might not happen.");  
```  
  
 Selbst wenn nichts im using-Block eine Ausnahme auslöst oder alle Ausnahmen im using-Block abgefangen werden, wird `Console.Writeline` möglicherweise nicht ausgeführt, da der implizite `Dispose`()-Aufruf an der schließenden Klammer eine Ausnahme auslösen kann.  
  
 Das zweite Problem (in der `DemonstrateProblemUsingCanThrowAndMask`-Methode veranschaulicht) ist eine weitere Implikation der schließenden Klammer, die eine Ausnahme auslöst:  
  
```csharp   
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
    throw new ApplicationException("Hope this exception was not important, because "+  
                                   "it might be masked by the Close exception.");  
} // <-- this line might throw an exception.  
```  
  
 Da `Dispose`() in einem "finally"-Block auftritt, tritt `ApplicationException` nur außerhalb des using-Blocks auf, wenn bei `Dispose`() ein Fehler auftritt. Wenn der Code außen wissen muss, wann die `ApplicationException` auftritt, kann das "using"-Konstrukt zu Problemen führen, da diese Ausnahme maskiert wird.  
  
 Abschließend wird im Beispiel veranschaulicht, wie die Bereinigung ordnungsgemäß ausgeführt wird, nachdem Ausnahmen in `DemonstrateCleanupWithExceptions` aufgetreten sind. Dabei wird ein try/catch-Block verwendet, um Fehler zu melden und `Abort` aufzurufen. Finden Sie unter den [Ausnahmen erwartet](../../../../docs/framework/wcf/samples/expected-exceptions.md) Weitere Informationen zum Abfangen von Ausnahmen von clientaufrufen.  
  
```csharp   
try  
{  
    ...  
    client.Close();  
}  
catch (CommunicationException e)  
{  
    ...  
    client.Abort();  
}  
catch (TimeoutException e)  
{  
    ...  
    client.Abort();  
}  
catch (Exception e)  
{  
    ...  
    client.Abort();  
    throw;  
}  
```  
  
> [!NOTE]
>  Die using-Anweisung und ServiceHost: Viele selbst gehostete Anwendungen nur wenig mehr als einen Dienst hosten, und ServiceHost.Close nur selten eine Ausnahme auslöst, damit die Verwendung solcher Anwendungen sicher verwenden können-Anweisung mit ServiceHost. Achten Sie jedoch darauf, dass ServiceHost.Close eine `CommunicationException` auslösen kann. Wenn die Anwendung daher nach dem Schließen von ServiceHost fortgesetzt wird, sollten Sie die Verwendung der using-Anweisung vermeiden und sich an das zuvor beschriebene Muster halten.  
  
 Wenn Sie das Beispiel ausführen, werden die Antworten und Ausnahmen für den Vorgang im Konsolenfenster des Clients angezeigt.  
  
 Im Clientprozess werden drei Szenarios ausgeführt, die jeweils versuchen, `Divide` aufzurufen. Im ersten Szenario wird veranschaulicht, dass Code aufgrund einer Ausnahme von `Dispose`() übersprungen wird. Im zweiten Szenario wird veranschaulicht, dass eine wichtige Ausnahme aufgrund einer Ausnahme von `Dispose`() maskiert wird. Das dritte Szenario zeigt die ordnungsgemäße Bereinigung.  
  
 Die erwartete Ausgabe vom Clientprozess lautet wie folgt:  
  
```  
=  
= Demonstrating problem:  closing brace of using statement can throw.  
=  
Got System.ServiceModel.CommunicationException from Divide.  
Got System.ServiceModel.Security.MessageSecurityException  
=  
= Demonstrating problem:  closing brace of using statement can mask other Exceptions.  
=  
Got System.ServiceModel.CommunicationException from Divide.  
Got System.ServiceModel.Security.MessageSecurityException  
=  
= Demonstrating cleanup with Exceptions.  
=  
Calling client.Add(0.0, 0.0);  
        client.Add(0.0, 0.0); returned 0  
Calling client.Divide(0.0, 0.0);  
Got System.ServiceModel.CommunicationException from Divide.  
  
Press <ENTER> to terminate client.  
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
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`  
  
## <a name="see-also"></a>Siehe auch
