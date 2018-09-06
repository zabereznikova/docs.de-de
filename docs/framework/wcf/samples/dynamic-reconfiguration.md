---
title: Dynamische Neukonfiguration
ms.date: 03/30/2017
ms.assetid: b20786ae-cce6-4f91-b6cb-9cae116faf8b
ms.openlocfilehash: a147a1d6cf61001832661376363ecc850ecad309
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43741103"
---
# <a name="dynamic-reconfiguration"></a>Dynamische Neukonfiguration
Diesem Beispiel wird der Windows Communication Foundation (WCF)-Routingdienst veranschaulicht. Der Routingdienst ist eine WCF-Komponente, die es einfach macht, ein inhaltsbasierten Routers in Ihre Anwendung einbinden. In diesem Beispiel wird die standard-WCF--Rechnerbeispiel für die Kommunikation über den Routingdienst angepasst. In diesem Beispiel wird gezeigt, wie der Routingdienst während der Laufzeit dynamisch neu konfiguriert werden kann.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\DynamicReconfiguration`  
  
## <a name="sample-details"></a>Beispieldetails  
 Damit der Routingdienst während der Laufzeit dynamisch neu konfiguriert werden kann, wird in diesem Beispiel alle fünf Sekunden ein Timer ausgelöst, mit dem ein neues <xref:System.ServiceModel.Routing.RoutingConfiguration>-Objekt erstellt und angewendet wird. Diese Konfiguration verweist entweder auf den reguläre Rechnerendpunkt oder auf den Rundungsrechnerendpunkt. Die Meldungen der Rechnerclientanwendung werden von einem der beiden Dienste zurückgegeben, abhängig davon, auf welchem Dienst der Routingdienst für das Routing zu der jeweiligen Zeit konfiguriert ist.  
  
 Es wird die Funktion des Routingdiensts zur dynamischen Neukonfiguration über ein benutzerdefiniertes Verhalten verwendet. Mit diesem benutzerdefinierten Verhalten wird eine Diensterweiterung angefügt, die einen einfachen Threadtimer enthält. Der Timer wird alle fünf Sekunden ausgelöst und verursacht damit einen Rückruf zur `UpdateRules`-Methode. Mit dem Rückruf wird die neue Routingkonfiguration erstellt und übernommen. In einer tatsächlichen Bereitstellung würde dieser Rückruf wahrscheinlich als Ergebnis eines anderen Ereignistyps (z. B. einer SQL-Ereignisbenachrichtigung oder einer WS-Discovery-Ankündigung) erfolgen.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] DynamicReconfiguration.sln.  
  
2.  Zum Öffnen **Projektmappen-Explorer**Option **Projektmappen-Explorer** aus der **Ansicht** im Menü.  
  
3.  Drücken Sie **F5** oder **STRG + UMSCHALT + B** in Visual Studio.  
  
    1.  Wenn Sie möchten, um-die notwendigen Projekte automatisch gestartet, wenn Sie drücken **F5**mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Eigenschaften**. Wählen Sie die **Startprojekt** Knoten unter **allgemeine Eigenschaften** im linken Bereich. Wählen Sie die **mehrere Startprojekte** Optionsfeld aus, und legen Sie alle Projekte die **starten** Aktion.  
  
    2.  Wenn Sie das Projekt mit erstellen **STRG + UMSCHALT + B**, müssen Sie die folgenden Anwendungen starten:  
  
        1.  Rechnerclient (./CalculatorClient/bin/client.exe)  
  
        2.  Rechnerdienst (./CalculatorService/bin/service.exe)  
  
        3.  Routingrechnerdienst (./RoundingCalcService/bin/service.exe)  
  
        4.  Routingdienst (./RoutingService/bin/RoutingService.exe)  
  
4.  Drücken Sie im Konsolenfenster des Rechnerclients die EINGABETASTE, um den Client zu starten und die Rechnerdienstvorgänge aufzurufen.  
  
     Der Routingdienst leitet abwechselnd Meldungen an den Rundungsrechner und den regulären Rechner, da die Routingkonfiguration sich alle fünf Sekunden ändert. Abhängig davon, an welchen Endpunkt der Routingdienst Meldungen laut Konfiguration senden soll, ist die Ausgabe im Clientkonsolenfenster jeweils unterschiedlich.  
  
5.  Drücken Sie mindestens fünf Sekunden lang wiederholt die EINGABETASTE, und achten Sie auf die Änderung der Ergebnisse des Diensts.  
  
    1.  Die zurückgegebene Ausgabe, wenn der Routerdienst zum Routen von Meldungen an den Rundungsrechnerdienst konfiguriert ist, sieht folgendermaßen aus:  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.2  
        Divide(22,7) = 3.1  
        ```  
  
    2.  Die zurückgegebene Ausgabe, wenn der Routingdienst zum Routen von Meldungen an den regulären Rechnerdienst konfiguriert ist, sieht folgendermaßen aus:  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
6.  Vom Rechnerdienst und der Rundungsrechnerdienst wird außerdem ein Protokoll der Vorgänge gedruckt, die in den jeweiligen Konsolenfenstern aufgerufen werden.  
  
7.  Klicken Sie im Konsolenfenster Clients geben Sie "quit", und drücken Sie EINGABETASTE zum Beenden.  
  
8.  Drücken Sie die EINGABETASTE in den Dienstkonsolenfenstern, um die Dienste zu beenden.  
  
## <a name="scenario"></a>Szenario  
 In diesem Beispiel wird der Router als inhaltsbasierter Router dargestellt, der ermöglicht, dass mehrere Typen oder Implementierungen von Diensten über einen Endpunkt verfügbar gemacht werden.  
  
### <a name="real-world-scenario"></a>Reales Szenario  
 Contoso möchte sämtliche Dienste virtualisieren, um nur einen Endpunkt öffentlich verfügbar zu machen, über den Zugriff auf mehrere verschiedene Dienste gewährt wird. In diesem Fall werden die inhaltsbasierten Routingfunktionen des Routingdiensts verwendet, um zu bestimmen, wohin die eingehenden Anforderungen gesendet werden sollen.  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting- und-persistenzbeispiele](https://go.microsoft.com/fwlink/?LinkId=193961)
