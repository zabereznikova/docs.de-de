---
title: "Vermeiden von Problemen mit der Using-Anweisung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Vermeiden von Problemen mit der Using-Anweisung
In diesem Beispiel wird veranschaulicht, wie Sie die C\#\-Anweisung "using" beim Verwenden eines typisierten Clients nicht zum automatischen Bereinigen von Ressourcen verwenden sollten.Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), das einen Rechnerdienst implementiert.In diesem Beispiel ist der Client eine Konsolenanwendung \(.exe\), und der Dienst wird von Internetinformationsdiensten \(IIS\) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel werden zwei häufige Probleme veranschaulicht, die beim Verwenden der C\#\-Anweisung "using" mit typisierten Clients auftreten. Außerdem wird Code bereitgestellt, mit dem die Bereinigung nach Ausnahmen korrekt ausgeführt werden kann.  
  
 Die C\#\-Anweisung "using" führt zu einem Aufruf von `Dispose`\(\).Dies ist das Gleiche wie `Close`\(\). Dies kann zu Ausnahmen führen, wenn ein Netzwerkfehler auftritt.Da der Aufruf von `Dispose`\(\) implizit an der schließenden Klammer des "using"\-Blocks erfolgt, wird diese Quelle für Ausnahmen beim Schreiben oder Lesen des Codes häufig nicht bemerkt.Dies stellt eine potenzielle Quelle für Anwendungsfehler dar.  
  
 Das erste Problem \(in der `DemonstrateProblemUsingCanThrow`\-Methode dargestellt\) liegt darin, dass die schließende Klammer eine Ausnahme auslöst und der Code nach der schließenden Klammer nicht ausgeführt wird:  
  
```  
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
} // <-- this line might throw  
Console.WriteLine("Hope this code wasn't important, because it might not happen.");  
```  
  
 Selbst wenn nichts im using\-Block eine Ausnahme auslöst oder alle Ausnahmen im using\-Block abgefangen werden, wird `Console.Writeline` möglicherweise nicht ausgeführt, da der implizite `Dispose`\(\)\-Aufruf an der schließenden Klammer eine Ausnahme auslösen kann.  
  
 Das zweite Problem \(in der `DemonstrateProblemUsingCanThrowAndMask`\-Methode veranschaulicht\) ist eine weitere Implikation der schließenden Klammer, die eine Ausnahme auslöst:  
  
```  
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
    throw new ApplicationException("Hope this exception was not important, because "+  
                                   "it might be masked by the Close exception.");  
} // <-- this line might throw an exception.  
```  
  
 Da `Dispose`\(\) in einem "finally"\-Block auftritt, tritt `ApplicationException` nur außerhalb des using\-Blocks auf, wenn bei `Dispose`\(\) ein Fehler auftritt.Wenn der Code außen wissen muss, wann die `ApplicationException` auftritt, kann das "using"\-Konstrukt zu Problemen führen, da diese Ausnahme maskiert wird.  
  
 Abschließend wird im Beispiel veranschaulicht, wie die Bereinigung ordnungsgemäß ausgeführt wird, nachdem Ausnahmen in `DemonstrateCleanupWithExceptions` aufgetreten sind.Dabei wird ein try\/catch\-Block verwendet, um Fehler zu melden und `Abort` aufzurufen.Detaillierte Informationen zum Abfangen von Ausnahmen von Clientaufrufen finden Sie im Beispiel [Erwartete Ausnahmen](../../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
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
>  Die using\-Anweisung und ServiceHost: Viele selbst gehostete Anwendungen führen wenige andere Aktionen als das Hosten eines Diensts aus, und ServiceHost.Close löst selten Ausnahmen aus. In solchen Anwendungen kann die using\-Anweisung mit ServiceHost daher sicher verwendet werden.Achten Sie jedoch darauf, dass ServiceHost.Close eine `CommunicationException` auslösen kann. Wenn die Anwendung daher nach dem Schließen von ServiceHost fortgesetzt wird, sollten Sie die Verwendung der using\-Anweisung vermeiden und sich an das zuvor beschriebene Muster halten.  
  
 Wenn Sie das Beispiel ausführen, werden die Antworten und Ausnahmen für den Vorgang im Konsolenfenster des Clients angezeigt.  
  
 Im Clientprozess werden drei Szenarios ausgeführt, die jeweils versuchen, `Divide` aufzurufen.Im ersten Szenario wird veranschaulicht, dass Code aufgrund einer Ausnahme von `Dispose`\(\) übersprungen wird.Im zweiten Szenario wird veranschaulicht, dass eine wichtige Ausnahme aufgrund einer Ausnahme von `Dispose`\(\) maskiert wird.Das dritte Szenario zeigt die ordnungsgemäße Bereinigung.  
  
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
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`  
  
## Siehe auch