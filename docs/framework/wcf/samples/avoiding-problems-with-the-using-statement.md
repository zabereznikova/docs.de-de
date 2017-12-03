---
title: Vermeiden von Problemen mit der Using-Anweisung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2921602376879d741c0873ba8730258c6dcc903f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="avoiding-problems-with-the-using-statement"></a>Vermeiden von Problemen mit der Using-Anweisung
In diesem Beispiel wird veranschaulicht, wie Sie die C#-Anweisung "using" beim Verwenden eines typisierten Clients nicht zum automatischen Bereinigen von Ressourcen verwenden sollten. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , implementiert einen rechnerdienst. In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel werden zwei häufige Probleme veranschaulicht, die beim Verwenden der C#-Anweisung "using" mit typisierten Clients auftreten. Außerdem wird Code bereitgestellt, mit dem die Bereinigung nach Ausnahmen korrekt ausgeführt werden kann.  
  
 Die C#-Anweisung "using" führt zu einem Aufruf von `Dispose`(). Dies ist das Gleiche wie `Close`(). Dies kann zu Ausnahmen führen, wenn ein Netzwerkfehler auftritt. Da der Aufruf von `Dispose`() implizit an der schließenden Klammer des "using"-Blocks erfolgt, wird diese Quelle für Ausnahmen beim Schreiben oder Lesen des Codes häufig nicht bemerkt. Dies stellt eine potenzielle Quelle für Anwendungsfehler dar.  
  
 Das erste Problem (in der `DemonstrateProblemUsingCanThrow`-Methode dargestellt) liegt darin, dass die schließende Klammer eine Ausnahme auslöst und der Code nach der schließenden Klammer nicht ausgeführt wird:  
  
```  
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
} // <-- this line might throw  
Console.WriteLine("Hope this code wasn't important, because it might not happen.");  
```  
  
 Selbst wenn nichts im using-Block eine Ausnahme auslöst oder alle Ausnahmen im using-Block abgefangen werden, wird `Console.Writeline` möglicherweise nicht ausgeführt, da der implizite `Dispose`()-Aufruf an der schließenden Klammer eine Ausnahme auslösen kann.  
  
 Das zweite Problem (in der `DemonstrateProblemUsingCanThrowAndMask`-Methode veranschaulicht) ist eine weitere Implikation der schließenden Klammer, die eine Ausnahme auslöst:  
  
```  
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
    throw new ApplicationException("Hope this exception was not important, because "+  
                                   "it might be masked by the Close exception.");  
} // <-- this line might throw an exception.  
```  
  
 Da `Dispose`() in einem "finally"-Block auftritt, tritt `ApplicationException` nur außerhalb des using-Blocks auf, wenn bei `Dispose`() ein Fehler auftritt. Wenn der Code außen wissen muss, wann die `ApplicationException` auftritt, kann das "using"-Konstrukt zu Problemen führen, da diese Ausnahme maskiert wird.  
  
 Abschließend wird im Beispiel veranschaulicht, wie die Bereinigung ordnungsgemäß ausgeführt wird, nachdem Ausnahmen in `DemonstrateCleanupWithExceptions` aufgetreten sind. Dabei wird ein try/catch-Block verwendet, um Fehler zu melden und `Abort` aufzurufen. Finden Sie unter der [Ausnahmen erwartet](../../../../docs/framework/wcf/samples/expected-exceptions.md) ausführliche Informationen zum Abfangen von Ausnahmen von Clientaufrufe Sample.  
  
```  
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
>  Die using-Anweisung und ServiceHost: Viele selbst gehostete Anwendungen führen wenige andere Aktionen als das Hosten eines Diensts aus, und ServiceHost.Close löst selten Ausnahmen aus. In solchen Anwendungen kann die using-Anweisung mit ServiceHost daher sicher verwendet werden. Achten Sie jedoch darauf, dass ServiceHost.Close eine `CommunicationException` auslösen kann. Wenn die Anwendung daher nach dem Schließen von ServiceHost fortgesetzt wird, sollten Sie die Verwendung der using-Anweisung vermeiden und sich an das zuvor beschriebene Muster halten.  
  
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
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`  
  
## <a name="see-also"></a>Siehe auch
